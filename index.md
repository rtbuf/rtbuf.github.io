**rtbuf** is BSD licensed ANSI C for realtime signal processing.

It seems that these last years most programming action happens
in high level programming languages which rely on garbage collectors
to free memory. The problem of a GC is that it induces latency
because while the program is stopped collecting free memory it
stops other processing so real-time applications are not possible
with most modern programming languages. Multi-processor safe and
real-time garbage collectors are not open source and very expensive
pieces of software.

A possible solution to handle real time computation on a garbage
collected platform is to offload real-time computations to a C server
running **rtbuf** which has no garbage collector and is highly portable.

Possible applications include audio and video applications, games and
experimental setups.

Current audience is developers. Status : alpha.

See the project page on Github :
[https://github.com/rtbuf/rtbuf](https://github.com/rtbuf/rtbuf)

## Compilation from sources

```
./autogen.sh && ./configure && make
```

## Installation

By default **rtbuf** gets installed into `$HOME/.rtbuf/` prefix.
```
make install
```

## Documentation

[Rtbuf Procedures Reference](/procedures-reference)

[Rtbuf C API](/c-api)

[Rtbuf Command line interface](/cli)

[Rtbuf GTK interface](/gtk)

## Libraries

**rtbuf** already contains several libraries :
 - **dynamic**   Dynamic range signal processing.
 - **glfw3**     Portable OpenGL, keyboard and mouse library.
 - **music**     Music functions.
 - **portaudio** Portaudio library for portable hardware audio i/o.
 - **signal**    Signal processing, operations on buffers of doubles.
 - **sndio**     OpenBSD sndio library for hardware audio i/o.
 - **synth**     A synthesizer collection.

## Procedures

Each library contains several named procedures.

Each procedure can be seen as a real time buffer object class.

A procedure has three methods :
 - **start** called before computation starts
 - **stop** called after computation has ended
 - **run** called at each tick of computation

See the [Rtbuf procedure reference](/procedures-reference).

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
