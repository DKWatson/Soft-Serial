# Soft-Serial

According to many open-source licenses, the code is free to use and so forth and so on. If however, you make changes to that code, you are obliged to post those changes. No problem.

The SoftwareSerial library for Arduino extends serial I/O to as many additional ports as you have spare pins. This is great and it works quite well. The only problem is that it takes control of the pin change interrupts and does not therefore play well with libraries that would avail themselves of those same capabilities.

I utilize quadrature encoders and rely on a pair of interrupts to detect activity. My library of choice for this is EnableInterrupt, alternately PinChangeInterrupt. Both allow you to clearly define NO interrupts on any of the available ports thereby creating smaller code as well as not disturbing the interrupt vectors for the unused ports. So would it be sufficient if SoftwareSerial had such a facility, but it does not.

To this end I hacked/butchered/chopped SoftwareSerial into three separate libraries: SSerialB, SSerialC and SSerialD (all for the Uno just now) that allow for the creation of software serial ports utilizing pins on the respective H/W ports only. The interrupt vectors are free for use elsewhere. The only known issue is that if you try to instantiate a port using other pins, there is no compile or run-time error, it simply doesn't work.

Anyhow, here they are. Feel free to use them as you see fit without any obligation to me.
