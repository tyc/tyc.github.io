---
layout: post
title:  "Can unit test replace a debugger?"
date:   2016-10-22 22:06:54 +0200
categories: unit_test 
---
I started working in embedded systems in 1992. At that time, I have wondered if it is possible to get your code working without the need of a debugger.


The debuggers I was using when I started was ICE [0]. By this I meant that the microcontroller was replaced with a special bonded out chip, and it's clocking was controlled. The ICE allow me full access to microcontroller’s operation and peripherals, almost down to controlling each clock cycle. I was able to see everything the microcontroller was able to see. Sometimes, the cache on the ICE was large enough that I was also able capture a log of the instruction sequences. This is very helpful when I had to double check the execution path leading up to a break point.

These days I work in a large engineering team with 32bit devices. The debuggers are usually interfaced via the JTAG connector. Although I can use it to debug my code, the control is not as fine as that of an ICE. The direction seems to be heading towards higher level of abstraction. Only use a debugger when it is necessary to. With a typical layered architecture, this is workable.

Extrapolating it further, is it possible to do a full project without any access to a debugger? In many projects, these is already occurring. The large amount of work from the ESP8266 [1] scene, the majority of the code are developed without a debugger. Yet this is in the hobbyist or prototype domain. What about the professional domain? To remove the debugger from the development tool chain would be difficult, especially if I am debugging code that is close to the metal. However, the higher up the software stack my code is residing in, reliance on it is getting smaller.

Using a unit test frame, the main advantage is to de-couple its dependency from the hardware and its maturity level. It may be possible for the software to be completed and released before the hardware is manufactured. Provided the behavior of the hardware is well known, this is a good strategy for reducing development time.

For the debugger, its major strength is to allow the code to be debugged close to the microcontroller. If I need to double check any data from the hardware, a debugger is essential. This is one area a unit test framework can never accomplish. The hardware may be mocked, but the mocked behavior will need to be verified against the hardware.

[0] – In circuit emulator. http://www.ganssle.com/articles/BegincornerICE.htm
[1] – https://en.wikipedia.org/wiki/ESP8266

---

I have written a Guide to Successful Unit Tests.
You can get it here at [Leanpub][leadpub_sut] and read about these topics and more.

[leadpub_sut]: https://leanpub.com/successfulunittest/