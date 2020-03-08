# RTBUF Type Reference

-----

## C types

### double
[Double-precision floating-point format](https://en.wikipedia.org/wiki/Double-precision_floating-point_format).

-----

## Signal types

### Signal sample
A signal sample is defined to be a 64 bit double float.
```
typedef double t_rtbuf_signal_sample;
#define RTBUF_SIGNAL_SAMPLE_SIZE sizeof(t_rtbuf_signal_sample)
#define RTBUF_SIGNAL_SAMPLE_TYPE "double"
```

### Signal
A signal is an array of `RTBUF_SIGNAL_SAMPLES` samples.
```
#define RTBUF_SIGNAL_SAMPLES     1024
typedef t_rtbuf_signal_sample t_rtbuf_signal[RTBUF_SIGNAL_SAMPLES];
#define RTBUF_SIGNAL_SIZE sizeof(t_rtbuf_signal)
```

