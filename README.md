# Differential-SPI-over-Ethernet
Board that natively plugs into PMOD 6x2 headers from Digilent FPGA dev boards, and converts it to 2 differential SPI channels sent out to RJ45 connectors to be transmitted for long runs over ethernet cables.

The board is meant to drive 2 SPI channels differentially over ethernet cables, and plugs into those "PMOD" connectors that all the FPGA dev boards have (but they are just 6x2 R/A 100mil headers, so also compatible with dupont/breadboard wires).  Right now I have one SPI channel with 500kHz slew-rate-limited transceivers stuffed, and one with 15MHz ones, but the chips have an identical SOIC-8 footprint so it's just a BOM change to swap them around whichever way you like.  There are solder jumpers on the board that let you hook the transceivers up so that it works for either the host side or the client side (clk is an output on a SPI host, but an input on an SPI client board).  You can also try a UART-based communication system on this board by only hooking up some of the pins - it's worth mentioning that many modern MCUs can do "UART" at over 10MHz, so theoretically if this link is just between an FPGA and one of those MCUs there are no restrictions to conventional UART baud rates, and UART would use 1/2 the pins of SPI.  Although I do love how SPI seems just made to work over RJ45 and ethernet cables!

![3d_render_PMOD_differential_driver](https://github.com/user-attachments/assets/8a41997f-7bd9-428f-ae24-73851807031c)
