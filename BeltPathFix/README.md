# Introduction
Voron0 has dimensional/tolerance issue with belts riding on bearings. Belt should not be more than 6mm wide as there is maximum of 6mm (3mm per each bearing) space available for the belt. But most belts and especially Gates are usually a bit more than 6mm wide (6.0 - 6.2mm). This causes increased belt wear, strange noises and small fluctuations in belt tension when toolhead moves. According to my experiments, it also affects input shaper results.

# Fix
To fix the problem, shims between bearings are used. You will need a pack of ultrathin shims, which you can [purchase from AliExpress](https://www.aliexpress.com/item/1005005204413043.html).

![Ultrathin shims from AliExpress](/BeltPathFix/images/box_shims.jpeg)

The total height of Voron0 pulley stack, which consists of a shim, two bearings and another shim, is **9mm**. You have to keep this when doing any kind of modifications.
Another important thing is belt line. **Belt has to be fully horizontal during entire path.**

There are several solutions possible.

## Solution #1 (belt space: 6.4mm)
- Shim 0.3mm
- Bearing 4.0mm
- Shim 0.4mm
- Bearing 4.0mm
- Shim 0.3mm
