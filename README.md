# Serial Wire Viewer debug output on STM32F103C8

Add the following openocd option to direct trace output to /tmp/swo.log:

```
-c "tpiu config internal /tmp/swo.log uart off 8000000"
```

8000000 is the clock frequency.

For details see: http://openocd.org/doc/html/Architecture-and-Core-Commands.html search for "ARMv7-M specific commands" and look for "tpiu config"

use `less -r /tmp/swo.log` or `tail -f /tmp/swo.log` to read the output.

## printf is blocking
On a 8 MHz clock, "Hello World %d\n" took 400 microseconds,
with a 72 MHz clock, 92 us.

To send a single char at 72 MHz took 2.5 us. Note the non-linearity.
