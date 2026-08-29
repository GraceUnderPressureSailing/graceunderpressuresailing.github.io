---
layout: page
title: LogPrinter
permalink: /projects/logprinter/
---

# LogPrinter

**Status:** Complete — installed, automatically recording passages and printing snapshots
**Platform:** Raspberry Pi, Java 21
**Data source:** Digital Yacht NavLink2, raw NMEA 2000 over UDP

LogPrinter began with a simple objective: produce a useful physical ship's-log
entry from the data already present on the boat. It has grown into a small
appliance that also preserves the raw evidence needed to understand a passage
afterwards.

<figure class="project-hero">
  <img src="/assets/images/logprinter/installed-overview.jpg"
       alt="The LogPrinter printer installed in the chart-table instrument panel">
  <figcaption>
    The completed LogPrinter installation: the 58 mm printer is mounted in the
    chart-table instrument panel, with a live passage print visible.
  </figcaption>
</figure>

## What it does

- Receives and decodes selected NMEA 2000 messages.
- Maintains a coherent snapshot of the boat's current state.
- Uses the instrument-power signal to open and close a passage automatically.
- Formats compact output for a 58 mm thermal printer.
- Records the original raw message stream without replacing it with summaries.
- Replays recordings through the same processing path used for live data.
- Produces passage summaries and exports GPS tracks for review in OpenCPN.

## Current installation

The Pi is intended to remain powered. It runs LogPrinter as a `systemd` service
and listens for the NMEA UDP feed, while an isolated relay contact tells it
whether the boat's instrument network is on. The contact pulls GPIO 17 low
against the Pi's internal pull-up; no instrument-bus voltage is applied to the
GPIO.

When the instruments come on, LogPrinter starts a new timestamped passage and
raw NMEA capture. When they go off, it closes the capture and finalises the
passage summary, but leaves the service ready for the next trip. An end-to-end
test aboard on 17 August 2026 created a new capture, grew it while the
instruments were active, and left the closed 206 KB file unchanged after they
were switched off.

The 58 mm printer is now connected and enabled as a second output alongside
the raw capture. A first live print test produced a clean result, and the
installed service is configured to print a compact snapshot after the first
minute, then every 30 minutes, while retaining the complete raw NMEA passage
log for later replay and analysis.

<div class="image-pair">
  <figure>
    <img src="/assets/images/logprinter/chart-table-location.jpg"
         alt="Grace Under Pressure's chart table and instrument panel">
    <figcaption>
      The chart table and instrument panel. The appliance lives behind this
      area, close to power and the vessel's navigation electronics.
    </figcaption>
  </figure>
  <figure>
    <img src="/assets/images/logprinter/prototype-assembly.jpg"
         alt="Raspberry Pi, DC to DC converter and isolated input assembled on a mounting board">
    <figcaption>
      An earlier assembly stage used to work out the regulated 5 V supply,
      terminal access and isolated instrument-power signal before installation.
    </figcaption>
  </figure>
</div>

<div class="image-pair">
  <figure>
    <img src="/assets/images/logprinter/raspberry-pi-wiring.jpg"
         alt="The LogPrinter Raspberry Pi and USB wiring installed behind the instrument panel">
    <figcaption>
      The Raspberry Pi, USB printer connection and protected wiring installed
      behind the instrument panel.
    </figcaption>
  </figure>
  <figure>
    <img src="/assets/images/logprinter/printed-snapshot.jpg"
         alt="A LogPrinter thermal-paper passage snapshot from the installed printer">
    <figcaption>
      A live snapshot printed aboard, showing the compact sailor-facing output
      produced from the boat data.
    </figcaption>
  </figure>
</div>

## Design priorities

The raw capture is kept separate from the interpreted boat state. New decoders
can therefore be added later without losing information that was not understood
at recording time. Live and replay operation share the same passage lifecycle,
which makes recorded-data testing representative of the appliance aboard the
boat.

The system is deliberately supplemental. Failure of the Pi, printer, network or
software must not affect the vessel's navigation equipment or controls.

## Evidence from a passage

The first full Raspberry Pi benchmark recorded the Brighton-to-Portsmouth
passage on 18 July 2026:

- approximately 9.5 hours and 3.25 million raw NMEA lines;
- a 43.45 nautical-mile GPX track containing 23,113 points;
- one material 76-second recording interruption;
- independent GPS sources from the Axiom plotter and Ray63 VHF;
- AIS reports representing hundreds of distinct targets; and
- a continuous, plausible barometric-pressure trend.

That recording demonstrated both the value of retaining the raw stream and the
importance of marking gaps rather than silently interpolating across them.

## Source

The software and technical installation material live in the
[LogPrinter repository](https://github.com/GraceUnderPressureSailing/LogPrinter).

> **Not for navigation:** LogPrinter, its exports and any passage illustrations
> are historical and supplemental. They must not be relied upon for navigation,
> collision avoidance or compliance with carriage requirements.
