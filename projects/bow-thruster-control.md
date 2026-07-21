---
layout: page
title: Rebuilding the bow-thruster control
permalink: /projects/bow-thruster-control/
---

<p class="project-deck">From a sticking button to a serviceable control</p>

**Status (July 2026):** Replacement switches selected and the new faceplate
ordered; installation and commissioning still to come.

<figure class="project-hero">
  <img src="/assets/images/bow-thruster/grace-under-pressure-sailing.jpg"
       alt="Grace Under Pressure sailing off the Sussex coast">
  <figcaption><em>Grace Under Pressure</em>, the reason for all the pieces of boat on the workbench.</figcaption>
</figure>

This project began with a sticky button on the Quick THC1022 bow-thruster
control fitted beside the starboard plotter. It became an investigation into
what had actually failed, which parts of the original system were worth
retaining, and how to replace the exposed controls without discarding sound
electronics and their existing control logic.

It is a record of one repair on one Jeanneau Sun Odyssey 440—not a wiring recipe
for another boat.

## The symptoms

The red, port button first became stuck in deposits around the switch tube. The
red cap came away while the button was being freed, leaving the switch working
but far too easy to operate. The more serious event came later: the green,
starboard button stuck down while the thruster was in use.

<figure>
  <img src="/assets/images/bow-thruster/original-control-failed-button.jpg"
       loading="lazy"
       alt="Original Quick THC1022 control with its red button cap missing and deposits around both switches">
  <figcaption>The starting point: one missing cap, one badly aged cap, and substantial deposits around both moving assemblies.</figcaption>
</figure>

A button which can remain operated is not merely cosmetic damage. During
close-quarters manoeuvring it can command unexpected continued thrust, and it
therefore needed treating as a functional safety fault.

## First, work out how it comes apart

There were no visible fasteners on the front and the rear of the controller
showed four threaded ends. Before finding the documentation it was unclear
whether these were studs, locating pins, hidden screws, or part of an adhesive
mounting arrangement.

<figure>
  <img src="/assets/images/bow-thruster/control-rear-mounting.jpg"
       loading="lazy"
       alt="Rear of the installed Quick bow-thruster controller showing its cylindrical housing and four threaded fasteners">
  <figcaption>The rear view prompted rather more speculation than it deserved.</figcaption>
</figure>

The installation instructions settled the question. The printed top is a
removable overlay; lifting it exposes four screws inserted from the front. No
hammer, hidden clips or structural sealant were involved.

<div class="image-pair">
  <figure>
    <img src="/assets/images/bow-thruster/overlay-removed.jpg"
         loading="lazy"
         alt="Quick controller with its black printed overlay removed">
    <figcaption>The printed overlay removed.</figcaption>
  </figure>
  <figure>
    <img src="/assets/images/bow-thruster/installation-instructions.jpg"
         loading="lazy"
         alt="Quick installation drawing showing the THC1022 overlay and four front mounting screws">
    <figcaption>The drawing that ended the mounting mystery.</figcaption>
  </figure>
</div>

## What had actually failed

Once opened, the controller divided neatly into two very different stories.
The exposed switch assemblies were heavily contaminated and mechanically
degraded. The coloured caps had suffered years of ultraviolet exposure, while
chalky salt and spray deposits had accumulated around the moving parts.

<figure>
  <img src="/assets/images/bow-thruster/failed-switches.jpg"
       loading="lazy"
       alt="Removed original red and green switch assemblies showing heavy deposits and degraded caps">
  <figcaption>The failed parts: exposed mechanical switch assemblies after years at the helm.</figcaption>
</figure>

By contrast, the enclosure had done its job. The circular PCB, wiring,
connectors and buzzer were clean and apparently undamaged. The board is also
refreshingly simple. There was no evidence-based reason to replace the whole
controller.

<div class="image-pair">
  <figure>
    <img src="/assets/images/bow-thruster/controller-teardown.jpg"
         loading="lazy"
         alt="Disassembled Quick THC1022 showing the original switches, PCB, buzzer, connectors and housing">
    <figcaption>The complete assembly separated into its serviceable parts.</figcaption>
  </figure>
  <figure>
    <img src="/assets/images/bow-thruster/pcb-and-connectors.jpg"
         loading="lazy"
         alt="Clean circular Quick controller circuit board with buzzer and three two-pin connectors">
    <figcaption>The electronics were clean; the failure was outside them.</figcaption>
  </figure>
</div>

## The design decision

The replacement therefore keeps the original Quick PCB, buzzer, main cable,
connectors and control behaviour. Only the weather-exposed user interface is
being replaced.

The new switches are RS PRO AV01 illuminated momentary SPST units:

- red ring, stock number **111-6531**;
- green ring, stock number **111-6529**;
- 12 mm panel mounting;
- normally-open momentary contacts; and
- IP65/IP67 environmental ratings.

They fit the original 12.2 mm structural holes, but the factory controller used
a second cosmetic fascia with 15 mm openings and long projecting caps. Mounted
in the original backing plate, the new flush switches sit too low and their
bezels do not cover those larger openings. Spacer bushes could have made the
geometry work, but would retain an awkward stack of old parts.

The cleaner solution is a new external faceplate with the switches mounted
directly in it, while the original housing and electronics move immediately
behind the fibreglass console. This keeps the original cable and electronics in
almost the same place while replacing the entire exposed front.

## The new faceplate

The current manufacturing model is a small, passivated 316L stainless-steel
plate, 3 mm thick, with:

- two 12.2 mm switch openings;
- four clearance holes for through-bolting;
- rounded corners; and
- a small perimeter chamfer to remove the sharp laser-cut edge.

This also became a useful first exercise in parametric CAD: constrain the outer
dimensions, align and position the switch centres, add the mounting holes,
extrude the plate, then apply the corner fillets and edge chamfer. A STEP model
was sufficient for automated manufacturing quotes.

The original connectors will be retained through a short removable adapter
loom, avoiding cuts to the Quick PCB or its cable. The old switch contacts used
two black conductors and required no polarity. The original panel had one
indicator LED on the port control; the final behaviour of the two new LED rings
will be decided only after the supply and current limiting have been measured.

## What remains

At the time of writing, the switches are on hand and the stainless plate has
been ordered. The remaining work is to:

1. inspect the fabricated plate and confirm switch fit;
2. build and continuity-test the removable loom;
3. mount the retained controller behind the console;
4. verify command direction and released-switch behaviour with the thruster
   safely isolated;
5. complete controlled dockside commissioning; and
6. record the finished installation and any changes prompted by testing.

A push-on weather cover is also planned. The original failure appears to have
been driven at least as much by ultraviolet exposure and accumulated deposits
as by water ingress, so shielding the new controls while the boat is unattended
should be worthwhile.

## Lessons so far

- Find the installation instructions before applying force.
- Diagnose the failed layer rather than replacing the most expensive assembly.
- A sealed enclosure may have preserved electronics even when its exposed
  controls look dreadful.
- Standard, documented parts make a future repair easier.
- A sticking thruster command is a safety fault, not a cosmetic inconvenience.

> **Safety-critical system:** A bow thruster combines very high electrical
> currents with machinery capable of moving the vessel unexpectedly. The work
> described here is incomplete and has not yet passed final commissioning.
> Isolate all relevant supplies, follow the equipment manufacturer's
> instructions, and obtain competent marine-electrical assistance where
> appropriate.
