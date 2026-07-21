---
layout: page
title: LogPrinter
permalink: /projects/logprinter/
---

# LogPrinter

**Status:** In service
**Platform:** Raspberry Pi, Java 21
**Data source:** Digital Yacht NavLink2, raw NMEA 2000 over UDP

LogPrinter began with a simple objective: produce a useful physical ship's-log
entry from the data already present on the boat. It has grown into a small
appliance that also preserves the raw evidence needed to understand a passage
afterwards.

## What it does

- Receives and decodes selected NMEA 2000 messages.
- Maintains a coherent snapshot of the boat's current state.
- Produces compact output for a 58 mm thermal printer.
- Records the original raw message stream without replacing it with summaries.
- Replays recordings through the same processing path used for live data.
- Exports GPS tracks for passage review in OpenCPN.

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
