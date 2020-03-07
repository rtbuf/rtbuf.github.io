# RTBUF Procedure Reference

This is a work in progress. Please send pull requests.


## Dynamic
The `dynamic` library contains signal dynamic range processing functions.


### Dynamic Limiter
Limits the dynamic range of a signal.


## Signal
The `signal` library contains basic signal processing functions.
See
[rtbuf_signal.c](https://github.com/rtbuf/rtbuf/blob/master/rtbuf_signal.c)
for details.


### Signal Bandpass2
Butterworth second order band-pass filter.

Inputs :
 - signal (signal)
 - cutoff (signal)
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


### Signal Sinus
Generates a sinus signal at given frequency.
Phase starts at zero.


### Signal Square
Generates a square signal at given frequency and pulse width.
Phase starts at zero.
