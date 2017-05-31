---
layout: post
title:  "Cmocka and Cmake"
date:   2016-10-22 22:06:54 +0200
comments: true
categories: unit_test 
---
I am using `cmocka` as the unit test framework to illustrate the concepts used in my book “a Guide to Success Unit Tests”.

`cmocka` relies on `cmake` build system to help it build the `cmocka` dynamic library as well as the test scripts into executables. So `cmake` will have to be installed as well as `cmocka` for it work correctly.

`cmake` can be downloaded from http://www.cmake.org/download/

`cmocka` can be downloaded from https://cmocka.org/files/

The I am using a MacOS computer, so my references are from using that computer.

# Installing CMake

When installing `cmake`, many different packaging versions can be downloaded. Since my computer is a MacOS, I downloaded the .dmg package. After I have extracted and installed it, I added it path the `cmake` executable.

{% highlight text %}
 export PATH=/Applications/CMake.app/Contents/bin:$PATH
{% endhighlight %}

I test that it can find it by getting it to report is version number.

{% highlight text %}
 localhost:~ tehnyitchin$ ccmake --version
 ccmake version 3.3.0

 CMake suite maintained and supported by Kitware (kitware.com/cmake).

 localhost:~ tehnyitchin$
{% endhighlight %}

# Checking `cmocka` is working

Once you have downloaded `cmocka` and unpacked it, you can test if the `cmake` and `cmocka` are going to work correctly. The file README has the correct instructions. In the example below, I have unzipped `cmocka` into a directory called `cmocka`.

{% highlight text %}
 cd cmocka
 mkdir build
 cd build
 cmake ../.
 make
{% endhighlight %}

After the build, the test binaries are in subdirectory example. Executing one of the test binaries will execute the test scripts. Below is a execution of simple_test

{% highlight text %}
 localhost:example tehnyitchin$ ./simple_test
 [==========] Running 1 test(s).
 [ RUN ] null_test_success
 [ OK ] null_test_success
 [==========] 1 test(s) run.
 [ PASSED ] 1 test(s).
 localhost:example tehnyitchin$
{% endhighlight %}

---

I have written a Guide to Successful Unit Tests.
You can get it here at [Leanpub][leadpub_sut] and read about these topics and more.

[leadpub_sut]: https://leanpub.com/successfulunittest/