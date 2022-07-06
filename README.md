# minimal_clk

This is a version of the minimal_clk command line utility for Raspberry Pis originally from the pigpio library website [here](https://abyz.me.uk/rpi/pigpio/examples.html#Miscellaneous%20related%20code) with a very minimal set of code changes to support BCM2711 based Pis, like the Raspberry Pi 4 and Raspberry Pi Compute Module 4.

No attempt was made to clean up the original code in any way.

It is important to understand that unless you are using one of the noise-shaping MASH dividers intended for use with frequencies < 25MHz, you are limited to dividing the selected PLL source frequency by integer values only.  For example, you will not be able to get a CM4 to produce a 100MHz clock signal using PLLD (750MHz):  the closest you can come is (750 / 7) = 107.14MHz.  The utility will set DIVF but it will be ignored when MASH = 0.

