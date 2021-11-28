# Drive Downloader

This is a teach repository, where I will be exploring the capabilities
of C++ and CMake as modern development tools.

## Goals

1. Introduce dependency management to C++ development, even with C++'s
   complicated build ecosystem.  I'll do this using the FetchContent and
   ExternalProject features.
2. Explore C++ as a tool for our modern distributed computing world by
   interacting with the Google Drive REST API.
3. Explore the new C++20 concurrency features.  Java and C# have
   excellent concurrency features, and I want to see how well C++
   competes in that domain.  I also just want to learn how to use these
   features.

## How to Build It.

If I do this correctly, the only thing that you should need is CMake and
a working C++ development environment.  You'll need a fairly recent
version of CMake, but it should be as simple as:

    mkdir build
    cd build
    cmake ..
    make

## How to Participate

I'm streaming this process as I do it, at
https://www.twitch.tv/claydowling

I usually announce streaming on
[Twitter](https://twitter.com/ClayDowling), although often not very far
in advance.

You can see the streams on
[YouTube](https://youtube.com/playlist?list=PL2PptCZXIreeNIiQwzahplLHnP4VK-yex)
if you want to follow along.  These are *not* well produced explanations
of how to do this.  These are unedited streams of a senior developer
figuring out how to use a complex system.  They make a better cure for
insomnia than a teaching aid, but watching them might also help you to
realize that you're not as big of an imposter as you think.
