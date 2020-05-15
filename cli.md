
## rtbuf Command Line Interface

```

$ ./rtbuf                                                                 
rtbuf> help
Available commands :
 libs                        List loaded libraries.
 lib N                       Show library N.
 load LIB                    Load library LIB.
 buffers                     List buffers.
 buffer N                    Show buffer N.
 let VAR = buffer N          Set variable to buffer.
 new LIB                     Instanciate library procedure.
 let VAR = new LIB           Set variable to new instance.
 delete BUFFER               Unlink and delete BUFFER.
 bind SOURCE OUT DEST IN     Bind SOURCE OUT to DEST IN.
 unbind BUFFER IN            Unbind BUFFER IN.
 start                       Start run thread.
 stop                        Stop run thread.
 help                        Show this help message.
 exit                        Quit RTBUF.

```
