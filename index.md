# rtbuf : Real time buffers

rtbuf is BSD licensed ANSI C for realtime signal processing.

See the project page on Github :
[https://github.com/rtbuf/rtbuf](https://github.com/rtbuf/rtbuf)

## Documentation

[Rtbuf Procedures Reference](/procedures-reference)

[Rtbuf C API](/c-api)

[Rtbuf Command line interface](/cli)

[Rtbuf GTK interface](/gtk)

## Libraries

rtbuf already contains several libraries :
 - **dynamic**   Dynamic range signal processing.
 - **glfw3**     Portable OpenGL, keyboard and mouse library.
 - **music**     Music functions.
 - **portaudio** Portaudio library for portable hardware audio i/o.
 - **signal**    Signal processing, operations on buffers of doubles.
 - **sndio**     OpenBSD sndio library for hardware audio i/o.
 - **synth**     A synthesizer collection.

## Procedures

Each library contains multiple named procedures.

Each procedure can be seen as a real time buffer object class.

A procedure has three methods :
 - **start** called before computation starts
 - **stop** called after computation has ended
 - **run** called at each tick of computation

## Procedure reference

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
