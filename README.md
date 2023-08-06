# GNU VOR Tester
 test VOR receivers with GNU Radio (GRC graph) and HackRF One

## HackRF One as VOR Test (not for calibaration!)
Use a HackRF One, the RNU Radio GRC graph and generate a VOR test signal.

You can set the angle and change (to simulate the direction).

There is also a station "morse code", but not really a morse code: it just
generates pulses for the station name (just to have "sound").

It is a GRC Graph for the HackRF One:
connect via direct coax antenna cable, maybe with an attenuator.

## Remarks
The correctness depends on the stability of the HackRF One oscillator
(and phase stability for the generated clocks and RF signals).

Not sure anymore, if you can upgrade the HackRF One with a better OSC.
(I did an update, not sure, maybe on a Lime SDR).

## Diclaimer
You can use to feed RF signal to a VOR receiver.
But you CANNOT use to test, calibrate your VOR receiver in an airplane.
The tester is for use at home, to demonstrate ... only, not for maintaining
VOR receivers in real airplanes!

