# RTBUF Procedure Reference

This is a work in progress. Please send pull requests.

### Dynamic Limiter
Limits the dynamic range of a signal.

### Signal Sinus
Generates a sinus signal at given frequency.
Phase starts at zero.

### Signal Square
Generates a square signal at given frequency and pulse width.
Phase starts at zero.

## Real time buffers

From a library procedure you can instanciate real time buffers.

A real time buffer (rtbuf) has inputs and outputs.
A buffer output can be connected to another buffer's input.

Once you have created and connected buffers together you can start computation.

## Contributing

Fork and send pull requests at
[https://github.com/rtbuf/rtbuf](https://github.com/rtbuf/rtbuf)

Only ISC (BSD) licensed code will be accepted.

## Authors

 - Thomas de Grivel <thoxdg@gmail.com>
 - Judy Najnudel <judy.najnudel@gmail.com>
