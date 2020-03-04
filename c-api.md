# rtbuf : Real time buffers C API

## Compilation

First your program must link to librtbuf

`CFLAGS = -I/usr/local/include/rtbuf`
`LDFLAGS = -L/usr/local/lib -lrtbuf`

## Initialization

rtbuf must be initialized using `librtbuf_init`

> `int librtbuf_init (void)`
> 
> Initializes rtbuf library

## Loading libraries

If you want to use existing rtbuf libraries
you must first load them using `rtbuf_lib_load`

> `s_rtbuf_lib * rtbuf_lib_load (const char *name)`
>
> Loads the rtbuf library named `name`.

## Finding a library by name

If your library is already loaded you can still
find it by name using `rtbuf_lib_find`

## Finding a proc

Inside a library you can find a procedure by name
using `rtbuf_lib_find_proc`

## Creating real time buffers

Once you have a procedure you can instanciate a real time buffer
with `rtbuf_new`

> `int rtbuf_new (s_rtbuf_proc *rp)`
>
> Instanciates a new buffer with its own inputs and outputs.
> The inputs and outputs are initially disconnected.
> All outputs have their memory initialized to zero.

## Binding real time buffer outputs and inputs

Once you have created buffers you can bind a buffer's output
to another buffer's input, provided they have compatible types,
using `rtbuf_bind`.

> `void rtbuf_bind (unsigned int src, unsigned int out, s_rtbuf *dest, unsigned int in)`
>
> Binds rtbuf `src` output `out` to rtbuf `dest` input `in`
