=======
Erratum
=======

We found undesired behavior for Gen 1 devices of the TimeTagger4.

If there are three or more edges close together (within 6.6 ns) and the user did
only enable rising or falling edges but not both, some edges are reported with
the wrong polarity.

If your configuration enables both edges all output data is correct. If you only
need one type of edge (rising or falling) there are three simple workarounds:

a) Update the Firmware of your Gen 1 device to svn1187 or later.
b) | Enable both edges.
   | All output words will be correct and your software can ignore all data that
     doesn’t have the desired polarity.
c) | Enable only the desired edge polarity.
   | Ignore the polarity flag in the output data. You can trust that only edges with
     the desired polarity are output, even if the flag in the data word states the
     wrong polarity.