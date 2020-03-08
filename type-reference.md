# RTBUF Type Reference

-----

## C types

### double
64 bit
[Double-precision floating-point format](https://en.wikipedia.org/wiki/Double-precision_floating-point_format)
.

-----

## Signal types
See
[rtbuf_signal.h](https://github.com/rtbuf/rtbuf/blob/master/rtbuf_signal.h)
for details.

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
#define RTBUF_SIGNAL_TYPE RTBUF_SIGNAL_SAMPLE_TYPE "[1024]"
```

### Signal function
A signal function is a typed accessor to sample data.

A signal function can access sample data per frame from either
a single sample or from a signal
(an array of `RTBUF_SIGNAL_SAMPLES` samples).

```
typedef t_rtbuf_signal_sample
f_rtbuf_signal (const t_rtbuf_signal_sample *signal,
                unsigned int sample);

typedef struct rtbuf_signal_fun {
  f_rtbuf_signal *sample_fun;
  const t_rtbuf_signal_sample *signal;
} s_rtbuf_signal_fun;

void rtbuf_signal_zero (t_rtbuf_signal_sample *signal);
t_rtbuf_signal_sample

void rtbuf_signal_fun (s_rtbuf *rtb,
                       unsigned int in,
                       s_rtbuf_signal_fun *data);
```
