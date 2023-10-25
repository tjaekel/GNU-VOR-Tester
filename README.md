# GNU VOR Tester
 test VOR receivers with GNU Radio (GRC graph) and HackRF One

## HackRFOne as VOR Test (not for calibaration!)
Use a HackRFOne, the GNU Radio GRC graph and generate a VOR test signal.

You can set the angle and change (to simulate the direction, done via "Delay").

There is also a station "morse code", but not really a morse code: it just
generates pulses for the station name (just to have "sound").
The morse code sounds like "TTT".

It is a GRC Graph for the HackRFOne:
connect via direct coax antenna cable, potentially with an attenuator (do not kill your SDR Rx).

## Remarks
The correctness depends on the stability of the HackRFOne oscillator
(and phase stability for the generated clocks and RF signals).

Not sure anymore, if you can upgrade the HackRF One with a better OSC.
(I did an update, not sure, maybe on a LimeSDR).

## Diclaimer
You can use to feed RF signal to a VOR receiver.
But you CANNOT use to test, calibrate your VOR receiver in an airplane.
The tester is for use at home, study purposes, to demonstrate ... only, not for maintaining
VOR receivers in real airplanes!

## VOR Tx and Rx Demo
You can use the GRC graph "VOR_Tester_FINAL.grc" (let it run/play for a minute)
in order to create a recorded file.
This file can be played (as file source) via GRC graphs.
It demodulates the generated signal and via OBS knob you can figure out
what the location (FROM) the station was (via "VOR_playFile_Simulator2.grc").

ATTENTION: the receiver as "VOR_playFile_Simulator2.grc" will NOT work with a
a real SDR receiver, on a real VOR signal:
The internal waveforms are trimmed and the approach is not the right way on a live signal!

## Demodulate a recorded VOR file
The file "File_Analyzer.grc" is intended to demodulate a real live signal,
recorded with HackRFOne in the vinicity of a VOR (ELB, 117.2, in SoCal).
BUT!:
It works to hear the morse code, I get the 30 Hz reference and variable signals. But both 30 Hz sine waves are drifting: there is not a constant phase difference.
It is the graph itself, because it happens also with a GRC to generate a VOR signal as file. They drift as well.

## Demo ELB VOR
Take these files:
* "File_Analyzer.grc" - it uses recorded file "ELB_VOR_2MSPS.complex"
* unzip file "ELB_VOR_2MSPS.zip" into "ELB_VOR_2MSPS.complex"
* play the graph: you should hear the morse code "ELB" and see the 30 Hz signals on scope
* the "phase difference measurement" is not done (because of the drifting phases, will not work anyway)

If you like to generate your own file (or transmit one, e.g. via HackRFOne):
* use "VOR_Test_FINAL.grc"
* it records to a file
* you can change the "File Sink" with your SDR dongle Tx (gr_osmosdr on older GRC versions, soapy on newer)
* you can also generate a file and demodulate again from file (no real SDR dongle needed)

I have used GRC 3.8 (older, with gr_osmosdr) and GRC 3.10 (with soapy). The graphs are intended for GRC 3.10.
(sometimes you do not have some blocks, e.g. gr_osmosdr is just in V3.8, or you have to set the Window again when changing the
GRC version).

