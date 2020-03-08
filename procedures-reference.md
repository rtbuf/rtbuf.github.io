# RTBUF Procedure Reference

-----

## Dynamic
Signal dynamic range processing functions.


### Dynamic Limiter
Limits the dynamic range of a signal.

Inputs :
 - signal (signal)
 - gain (signal)
 - treshold (signal)
 - attack (signal) *Attack time in seconds.*
 - release (signal) *Release time in seconds.*

Outputs :
 - signal (signal)

-----

## Portaudio
[PortAudio](http://www.portaudio.com/)
library for portable hardware audio I/O.


### Portaudio Input
TODO


### Portaudio Output
Stereo output using
[PortAudio](http://www.portaudio.org/)
.

Inputs :
 - left (signal)
 - right (signal)

Outputs :
 - samples (short[2048]) *Sample data in PortAudio format.*

-----

## Signal
Basic signal processing functions.

See
[rtbuf_signal.c](https://github.com/rtbuf/rtbuf/blob/master/rtbuf_signal.c)
for details.


### Signal Bandpass2
Butterworth second order band-pass filter.

Inputs :
 - signal  (signal)
 - cutoff  (signal)
 - qfactor (signal)

Outputs :
 - signal (signal)


### Signal Delay
Non-interpolating simple delay line.

Inputs :
 - signal (signal)
 - delay (signal) *Delay time in seconds. [0, RTBUF_SIGNAL_DELAY_MAX]*
 - feedback (signal) *Feedback. [0, 1]*

Outputs :
 - signal (signal)


### Signal Equalizer10
10 band Butterworth second order band-pass filters and their output.

Inputs :
 - signal (signal)
 - amp32  (signal) *Amplification at 32 Hz. [0, 2]*
 - amp64  (signal) *Amplification at 64 Hz. [0, 2]*
 - amp128 (signal) *Amplification at 128 Hz. [0, 2]*
 - amp256 (signal) *Amplification at 256 Hz. [0, 2]*
 - amp512 (signal) *Amplification at 512 Hz. [0, 2]*
 - amp1k  (signal) *Amplification at 1 kHz. [0, 2]*
 - amp2k  (signal) *Amplification at 2 kHz. [0, 2]*
 - amp4k  (signal) *Amplification at 4 kHz. [0, 2]*
 - amp8k  (signal) *Amplification at 8 kHz. [0, 2]*
 - amp16k (signal) *Amplification at 16 kHz. [0, 2]*

Outputs :
 - signal    (signal)
 - signal32  (signal) *Signal at 32 Hz.*
 - signal64  (signal) *Signal at 64 Hz.*
 - signal128 (signal) *Signal at 128 Hz.*
 - signal256 (signal) *Signal at 256 Hz.*
 - signal512 (signal) *Signal at 512 Hz.*
 - signal1k  (signal) *Signal at 1 kHz.*
 - signal2k  (signal) *Signal at 2 kHz.*
 - signal4k  (signal) *Signal at 4 kHz.*
 - signal8k  (signal) *Signal at 8 kHz.*
 - signal16k (signal) *Signal at 16 kHz.*


### Signal Flanger
Flanger effect.
Mixes dry signal with delayed signal.

Inputs :
 - signal (signal)
 - frequency (signal) *Delay oscillator frequency. [0, 24000]*
 - amplitude (signal) *Delay oscillator amplitude. [0, 1]*
 - delay     (signal) *Minimum delay. [0, 1]*
 - feedback  (signal) *Delay feedback. [0, 1]*

Outputs :
 - signal (signal)


### Signal Hipass
### Signal Hipass2
### Signal Hipass3
### Signal Hipass4
### Signal Hipass5
Butterworth first, second, third, fourth and fifth order high-pass filters.

Cuts frequencies lower than cutoff.

Inputs :
 - signal (signal)
 - cutoff (signal) *Cutoff frequency. [0, 24000]*

Outputs :
 - signal (signal)


### Signal Lopass
### Signal Lopass2
### Signal Lopass3
### Signal Lopass4
### Signal Lopass5
Butterworth first, second, third, fourth and fifth order low-pass filters.

Cuts frequencies higher than cutoff.

Inputs :
 - signal (signal)
 - cutoff (signal) *Cutoff frequency. [0, 24000]*

Outputs :
 - signal (signal)


### Signal Sawtooth
Generates a sawtooth signal at given frequency.
Phase starts at zero.

Inputs :
 - frequency (signal) *[0, 24000]*
 - amplitude (signal) *[0, 1]*

Outputs :
 - signal (signal)


### Signal Sinus
Generates a sinus signal at given frequency.
Phase starts at zero.

Inputs :
 - frequency (signal) *[0, 24000]*
 - amplitude (signal) *[0, 1]*

Outputs :
 - signal (signal)


### Signal Square
Generates a square signal at given frequency and pulse width.
Phase starts at zero.

Inputs :
 - frequency (signal) *[0, 24000]*
 - amplitude (signal) *[0, 1]*
 - pulse (signal) *Pulse width. [0, 1]*

Outputs :
 - signal (signal)

-----

## Sndio
OpenBSD
[sndio](http://www.sndio.org/)
library for hardware audio I/O.


### Sndio Input
TODO


### Sndio Output
Stereo output using
[sndio](http://www.sndio.org/)
.

Inputs :
 - left (signal)
 - right (signal)

Outputs :
 - samples (short[2048]) *Sample data in sndio format.*

-----

## Synth
A synthetizer collection.


### Synth ADSR
Attack decay sustain release enveloppe.

Inputs :
 - note (note) *Note. See rtbuf_music.h*
 - attack (signal) *Attack time in seconds.*
 - decay (signal) *Decay time in seconds.*
 - sustain (signal) *Sustain level.*
 - release (signal) *Release time in seconds.*

Outputs :
 - signal (signal)


### Synth Synth
Synthesizer.

Inputs :
 - envelope (signal) *Connect an enveloppe buffer which will be cloned for each note played.*
 - oscillator (signal) *Connect an oscillator buffer which will be cloned for each note played.*
 - note (notes) *Connect a keyboard notes here.*

Outputs :
 - signal (signal)
 - note_n (unsigned int) *Number of notes playing.*
