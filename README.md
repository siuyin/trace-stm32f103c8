# Serial Wire Viewer debug output on STM32F103C8

Add the following openocd option to direct trace output to /tmp/swo.log:

```
-c "tpiu config internal /tmp/swo.log uart off 8000000"
```

8000000 is the clock frequency.

For details see: http://openocd.org/doc/html/Architecture-and-Core-Commands.html search for "ARMv7-M specific commands" and look for "tpiu config"

use less -r /tmp/swo.log to read the output.

