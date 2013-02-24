High-Resolution Timer Interface
===============================

### Fingerprint 0x48525449 ('HRTI')

Under development.

The HRTI fingerprint allows a Funge program to measure elapsed time much
more finely than the clock values returned by `y`.

After successfully loading HRTI, the instructions `E`, `G`, `M`, `S`,
and `T` take on new semantics.

`G` 'Granularity' pushes the smallest clock tick the underlying system
can reliably handle, measured in microseconds.

`M` 'Mark' designates the timer as having been read by the IP with this
ID at this instance in time.

`T` 'Timer' pushes the number of microseconds elapsed since the last
time an IP with this ID marked the timer. If there is no previous mark,
acts like `r`.

`E` 'Erase mark' erases the last timer mark by this IP (such that `T`
above will act like `r`)

`S` 'Second' pushes the number of microseconds elapsed since the last
whole second.

The timer and mark-list are considered global and static, shared amongst
all IP's, in order to retain tame behaviour.

This timer is not affected by 'time travel' contrivances.
