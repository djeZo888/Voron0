_Note: This page is still being worked on!_
# Problem
Voron0 has dimensional/tolerance issue with belts riding on bearings. Belt should not be more than 6mm wide as there is maximum of 6mm (3mm per each bearing) space available for the belt. But most belts and especially Gates are usually a bit more than 6mm wide (6.0 - 6.2mm). This causes increased belt wear, strange noises and small fluctuations in belt tension when toolhead moves. According to my experiments, it also affects input shaper results.

[Listen to the belts making sound](/BeltPathFix/belt_rubbing_sound.m4a) when toolhead is being slowly moved by hand.

Damages to the belt caused by the problem are visible in the following pictures.
![Belt issue 1](/BeltPathFix/images/belt_damage_1.jpeg)
![Belt issue 2](/BeltPathFix/images/belt_damage_2.jpeg)

# Fix
The total height of Voron0 pulley stack, which consists of a shim, two bearings and another shim, is **9mm**. You have to keep this when doing any kind of modifications.

- Shim 0.5mm
- Bearing 4.0mm
- Bearing 4.0mm
- Shim 0.5mm

Another important thing is belt line. **Belt has to be fully horizontal during entire path.**

To fix the problem, shims between bearings are used. You will need a pack of ultrathin shims, which you can [purchase from AliExpress](https://www.aliexpress.com/item/1005005204413043.html).

![Ultrathin shims from AliExpress](/BeltPathFix/images/box_shims.jpeg)

Generally, the more space we can acquire for belt, the better. But there are limits. First is the total stack height which is 9mm. To keep the belt line, it is advised to do symetrical modifications. And lastly, stack has to start and end with a shim, so that bearings do not rub against plastic or metal parts of the printer.

There are several solutions possible.

## Solution #1 (belt space: 6.4mm)
- Shim 0.3mm
- Bearing 4.0mm
- Shim 0.4mm
- Bearing 4.0mm
- Shim 0.3mm

### Results
Belt | In theory | In practice
---|---|---
Gates 6.0-6.2mm | 6.4mm should be enough, but I'd recommend larger space if possible. | Tested, works OK with CNC parts.
Creality 5.7-5.9mm | There is 0.5-0.7mm of tolerance available, which is good. | Not tested.

## Solution #2 (belt space: 6.8mm)
_Note: this solution is not recommended for printed parts, as bearings may rub against plastic parts._
- Shim 0.1mm
- Bearing 4.0mm
- Shim 0.4mm
- Shim 0.4mm
- Bearing 4.0mm
- Shim 0.1mm

### Results
Belt | In theory | In practice
---|---|---
Gates 6.0-6.2mm | Best solution for Gates. | Not tested.
Creality 5.7-5.9mm | Should definitely work! | Not tested.
