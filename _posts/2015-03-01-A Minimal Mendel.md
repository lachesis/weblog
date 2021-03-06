---
title: "A Minimal Mendel, Postmortem"
tags: [self-Amos, mendelmin, reprap, prototyping]
---

The Prusa i2 design of 3D printer I had built with my friend <a href="https://alloscomp.com/">Eric</a> in 2013 was a great little 3D printer that can be built
with parts from the hardware store, but I felt that the design compromised too much. The triangular prism shaped frame of the i2 meant that it was extremely difficult to make the machine
perfectly square on all three axes. The Z axis was also over-constrained, which was a fundamental flaw in the design that made any eccentricity in the Z drive screws apparent as small ridges
on prints. There are a huge number of 3D printer designs out there; RepRaps and all the variations on that principle. I wanted a machine that would use the costly parts from
my Prusa i2, and transfer them to a simpler, stronger frame, while solving a number of other problems I found with the i2.

## My upgrade goals:

- More frame rigidity: a more rigid frame allows the machine to print faster and more accurately
- More Z print volume
- More accuracy
- More precision
- No Z-wobble
- No USB connectivity / interference errors
- A better filament feed system
- Easier bed levelling and Z home calibration
- Easier to assemble and disassemble without messing up calibration
- Compatibility with my extruder and hot-end (MakerGear Stepper Plastruder)

## Introducing the mendelmin

![mendelmin](http://i.imgur.com/45eCEDC.png)

At its core the mendelmin is a heavily modified <a href="http://reprap.org/wiki/MendelMax_2">MendelMax 2</a>, but with a smaller desk profile. It uses a right angle design made of 2020 extruded
aluminum sections, and laser-cut acrylic components. I moved the motors to the bottom of the frame, because top motors make it difficult to remove the X carriage assembly for maintenance.
Instead of a large double-decker base like the MendelMax, I have a single rectangular bottom frame, which gets extra rigidity from steel corner brackets, and T brackets at the vertical
intersection. The frame is absolutely solid during prints, and happily, the printer is much quieter as a result, even while running 25% faster. I experimented with using the aluminum sections
as the linear guide for the vertical axis, but I found that there was too much static friction between acrylic and the aluminum. This could have been solved with some PTFE bearing surfaces,
but I decided I wanted to keep the aluminum frame empty. That way, I could add on extras without interfering with the movement of the vertical axis.  The mendelmin has more print height,
230mm up from ~60mm on the Prusa i2. The Z-wobble issue is solved, thanks to drive nuts that freely float inside the Z carriage rather than being rigidly constrained. I added a housing for
an LCD Smart Controller, which allows the printer to load files directly from an SD card, eliminating USB interference errors that used to happened at random and would ruin prints.

## Where I fell short

Resorting to laser-cutting components is a major failure for an open-source 3D printer design in my opinion, because very few people have access to a laser cutter. It violates the core principle of a RepRap, which
is that one printer can make all the specialized hardware for another printer. I originally designed the components to be printable, but upon printing them I realized that my design required more precision
than my printer could accomplish. Bearings weren't perfectly aligned, and the printer didn't move smoothly.

My filament feed system is an upgrade from my Prusa i2, because the spool can freely rotate. Unfortunately the reality of coiled filament is that when it's unspooled from the same side for long enough,
torsional forces accumulate in the plastic and cause it to eventually tangle.

The X carriage is compatible with my extruder, but it isn't ideal. Many modern RepRap designs use a Bowden extruder, where the filament drive motor and gearing sits elsewhere on the printer, and the X carriage
only carries the hot-end. The motor and gearbox are quite heavy. The mendelmin X carriage weighs about 0.5kg, which is a large mass with a lot of inertia. The printer could be driven much faster designed with a
Bowden extruder. However, I decided to keep the stock configuration of the extruder, because it's a delicate and expensive part.

The print bed is the largest shortcoming of the mendelmin. I used the old HBP (heated build platform) from my i2, which mounts to the Y carriage at four points. This makes no sense, and needs to be revisited. A planar
surface is defined by three points, and any extra mounting points distort the build surface if they aren't precisely in plane. There are a number of existing compatible designs for Y carriages / build platforms,
so I will probably just use one of these. I also had in mind a bed levelling probe that would mount to the X carriage, but it was an extra feature that I cut from the final design. The X carriage didn't need extra weight.

## Success rate

I see this project as a success. It's not a perfect machine, but it ended up fully functional and an upgrade to my i2 in almost every way. Total cost to upgrade was roughly 200 dollars, which was pretty much exactly on budget.
I don't see this as a very viable design for other people, since it combines printed and laser-cut parts and requires very specific starting hardware (and a new builder could easily find cheaper and better parts to start with).
I came up with what think are a few elegant innovations, such as my Z endstop adjuster, which makes calibrating the Z home position very simple. 

You can find the mendelmin on <a href="http://www.thingiverse.com/thing:185402">Thingiverse</a>.




