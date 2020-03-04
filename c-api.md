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

## Starting up

Once your buffers are connected you can start computation
with `rtbuf_start`.

It will do a dependency sort on buffers and call their
procedure's start method on each buffer.

> `int rtbuf_start (void)`
>
> Initialize all buffers before calling `rtbuf_run`.
> 
> If any buffer fails to start then starting is aborted and
> the return value is non-zero.
>
> If all buffers were started successfully the function returns zero.

## Running

To compute all buffers use `rtbuf_run`.

Usually this function is called repeatedly in a main loop
until the application closes.

> `int rtbuf_run (void)`
>
> Runs computation on all buffers.
>
> If computation failed on any buffer the computation is halted
> and the return value is non-zero.
>
> If all buffers were computed successfully the function returns zero.
