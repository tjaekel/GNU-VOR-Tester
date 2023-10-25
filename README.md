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

## VOR Tx and Rx Demo
You can use the GRC graph "VOR_Tester_FINAL.grc" (let it run/play for a minute)
in order to create a file/
This file can be played (as file source) via "VOR_playFile_Simulator2.grc":
It will demodulate the generated signal and via OBS knob you can figure out
what the location (FROM) the station was.

ATTENTION: the receiver as "VOR_playFile_Simulator2,grc" will not work with a
a real SDR receiver, on a real VOR signal:
The internal waveforms are trimmed and not the right way on a live signal!

## Demodulate a recorded VOR file
The file "File_Analyzer.grc" is intended to demodulate a real live signal,
recorded with HackRFOne in the vinicity of a VOR (ELB, 117.2, in SoCal).
BUT!:
It works to hear the morse code, I get the 30 Hz reference and variable signals.But both 30 Hz sine waves are drifting: there is not a constant phase difference.
It is the graph itself, because it happens also with a GRC to generate a VOR signal. They drift as well.

