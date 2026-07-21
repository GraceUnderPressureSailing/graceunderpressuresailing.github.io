---
layout: default
title: Home
---

# Grace Under Pressure Sailing

## Practical boat systems, field engineering and passage notes

This is a working notebook from *Grace Under Pressure*: projects built for a
real boat, tested in service, and documented with the decisions, limitations
and failures left in.

The aim is to share useful evidence rather than universal instructions. Every
installation is different, and safety-critical work must be checked against
the equipment manufacturer's instructions and the requirements that apply to
the vessel concerned.

<div class="project-grid">
  <section class="project-card">
    <p class="status">IN SERVICE</p>
    <h3><a href="/projects/logprinter/">LogPrinter</a></h3>
    <p>A Raspberry Pi appliance that captures NMEA 2000 data, maintains a live
    picture of the boat, prints a compact ship's log and preserves passages for
    later analysis.</p>
  </section>

  <section class="project-card">
    <p class="status">WRITE-UP IN PROGRESS</p>
    <h3><a href="/projects/bow-thruster-control/">Bow-thruster control replacement</a></h3>
    <p>Replacing an ageing control system while retaining clear isolation,
    predictable operation and fail-safe behaviour.</p>
  </section>
</div>

## Publishing principles

- Separate what was observed from what has been inferred.
- State the equipment, software version and vessel context.
- Record tests and failure modes, not only the successful result.
- Correct and date material when experience changes the conclusion.

> **Important:** This site is informational and is not professional marine
> engineering or navigational advice. See the [safety and limitations](/safety/)
> page before relying on any technical material.
