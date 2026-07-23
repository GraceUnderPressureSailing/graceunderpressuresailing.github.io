---
layout: page
title: Rebuilding the bow-thruster control
permalink: /projects/bow-thruster-control/
---

<p class="project-deck">From a sticking button to a serviceable control</p>

**Status (July 2026):** Stainless faceplate and 16 mm switches installed. An
initial functional test confirmed that both thruster commands work; the
behind-console wiring shown below is still to be tidied and documented.

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

The first replacements were 12 mm RS PRO AV01 illuminated momentary switches.
Mechanically, they fitted the original structural plate beautifully. The
problem only became apparent when they were operated in their intended flush
position: the actuators were too narrow to press easily and confidently with a
finger. A control can be electrically correct and still fail an ergonomic test.

The final selection is the larger, pre-wired RS PRO MPB16 series:

- green illuminated momentary SPST, stock number **175-9549**;
- red illuminated momentary SPST, stock number **175-9392**;
- 16 mm panel mounting;
- normally-open momentary contacts;
- pre-wired tails; and
- IP67 environmental rating.

<figure>
  <img src="/assets/images/bow-thruster/prewired-16mm-switches.jpg"
       loading="lazy"
       alt="Pair of pre-wired 16 mm stainless illuminated momentary switches with their mounting nuts and seals">
  <figcaption>The final 16 mm switches arrived pre-wired, with separate conductors for their contacts and illuminated rings.</figcaption>
</figure>

Before that change, the 12 mm switches also exposed a mismatch in the factory
construction. The original structural plate had 12.2 mm holes, while a second
cosmetic fascia used 15 mm openings and long projecting caps. Mounted behind
that fascia, the flush replacements sat too low and their bezels did not cover
the larger openings. Spacer bushes could have made the geometry work, but would
retain an awkward stack of old parts.

The cleaner solution is a new external faceplate with the switches mounted
directly in it, while the original housing and electronics move immediately
behind the fibreglass console. This keeps the original cable and electronics in
almost the same place while replacing the entire exposed front.

## The new faceplate

The plate was manufactured in passivated 316L stainless steel, 3 mm thick,
with four through-bolt clearances, rounded corners and a small perimeter
chamfer. It was originally cut with two 12.2 mm switch openings; after the
ergonomic test, those were drilled to 16.2 mm to provide clearance for the
16 mm MPB16 switch barrels. The CAD model has now been updated to match.

<figure>
  <img src="/assets/images/bow-thruster/faceplate-assembled.jpg"
       loading="lazy"
       alt="Passivated stainless bow-thruster faceplate assembled on the bench with two 16 mm flush switches">
  <figcaption>The revised plate assembled on the bench. The larger actuators are much easier to operate confidently than the first 12 mm pair.</figcaption>
</figure>

### CAD model and downloads

- [Working faceplate model in Onshape](https://cad.onshape.com/documents/bab55f22eadae1309f6581ff/w/6a2407166261e4ce7e9ad419/e/d4661129cfbdfaf08c7402ee)
  (an Onshape account may be required).
- [Download the current AP242 STEP model](/assets/downloads/bow-thruster/bow-thruster-faceplate-16.2mm.step)
  (exported 21 July 2026).

> **Model status:** The current Onshape and STEP models use 16.2 mm switch
> openings. They document this one installation; verify every dimension,
> material and clearance against the intended switches and mounting location
> before using the file for manufacture.

This also became a useful first exercise in parametric CAD: constrain the outer
dimensions, align and position the switch centres, add the mounting holes,
extrude the plate, then apply the corner fillets and edge chamfer. A STEP model
was sufficient for automated manufacturing quotes.

The original connectors will be retained through a short removable adapter
loom, avoiding cuts to the Quick PCB or its cable. The old switch contacts used
two black conductors and required no polarity. The original panel had one
indicator LED on the port control.

Three 500 Ω, 0.5 W, 0.1% metal-film resistors (TE Connectivity
**UPF50B500RV**, RS stock **807-3762**) have been bought so that external LED
current limiting is available if required. The installation-stage circuit
proved that the switch contacts and illumination work with the retained Quick
controller. The final as-built record will document the current-limiting
arrangement after the wiring has been tidied, rather than attempting to infer it
from the temporary test connections.

## Physical installation

The new plate is through-bolted over the original opening beside the starboard
plotter and windlass control. The two switches mount directly through the
stainless plate, avoiding the recessed factory fascia and its stand-offs.

<figure>
  <img src="/assets/images/bow-thruster/faceplate-installed.jpg"
       loading="lazy"
       alt="New stainless bow-thruster control installed beside the starboard Raymarine plotter and Quick windlass control">
  <figcaption>The new control in its working position. The plate covers the former opening and the two flush switches remain easy to reach.</figcaption>
</figure>

The original Quick cylindrical enclosure, PCB, buzzer and main cable remain
immediately behind the console. This preserves the original control electronics
and provides a serviceable boundary between them and the replacement switches.
The lever connectors visible in the photograph were used for the installation
and functional test; this is not presented as the finished wiring arrangement.

<figure>
  <img src="/assets/images/bow-thruster/retained-controller-installed.jpg"
       loading="lazy"
       alt="Original Quick controller housing and PCB retained behind the console with temporary lever-connector wiring">
  <figcaption>Behind the console during testing: the healthy Quick controller retained, with the new switch wiring still awaiting its final tidy-up.</figcaption>
</figure>

Both directional commands and the switch illumination operated correctly in
the initial test. That proves the replacement interface and retained controller
work together; it does not remove the need to secure, protect, label and record
the finished wiring.

## What remains

At the time of writing, the new controls have passed an initial functional
test. The remaining work is to:

1. record the final LED current-limiting arrangement;
2. replace or tidy the installation-stage connections into a secured,
   strain-relieved loom;
3. secure and protect the retained controller and wiring behind the console;
4. label and continuity-test the finished arrangement;
5. repeat the released-switch and command-direction checks after the wiring is
   finalised; and
6. photograph and record the completed internal installation.

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
- A bench fit is not the same as a usable human interface; test the control with
  real fingers in its real mounting position.
- A sticking thruster command is a safety fault, not a cosmetic inconvenience.

> **Safety-critical system:** A bow thruster combines very high electrical
> currents with machinery capable of moving the vessel unexpectedly. The work
> shown here includes temporary installation-stage wiring and should not be
> treated as a wiring recipe or a finished installation. Isolate all relevant
> supplies, follow the equipment manufacturer's instructions, verify all
> functions after final assembly, and obtain competent marine-electrical
> assistance where appropriate.
