# SevenSeas

SevenSeas desktop wallet for PirateChain ($ARRR) that runs on Linux, Windows and macOS.
This is experimental software under active development!

![Screenshots](docs/screenshot.png?raw=true)

## PRIVACY NOTICE

SevenSeas contacts a few different external websites to get various
bits of data.
    * coingecko.com for price data API
    * explorer.pirate.black for explorer links
    * dexstats.info for address utilities

This means your IP address is known to these servers. Enable Tor setting
in SevenSeas to prevent this, or better yet, use TAILS: https://tails.boum.org/

# Installation

Head over to the releases page and grab the latest installers or binary. https://github.com/PirateNetwork/SevenSeas/releases

## pirated

SevenSeas needs a Pirate full node running pirated. If you already have a pirated node running, SevenSeas will connect to it. 

If you don't have one, SevenSeas will start its embedded pirated node. 

Additionally, if this is the first time you're running SevenSeas or a pirated daemon, SevenSeas will download the zcash params (~1.7 GB) and configure `PIRATE.conf` for you. 

Pass `--no-embedded` to disable the embedded pirated and force SevenSeas to connect to an external node.

## Compiling from source

SevenSeas is written in C++ 14, and can be compiled with g++/clang++/visual
c++. It also depends on Qt5, which you can get from
[here](https://www.qt.io/download). Note that if you are compiling from source,
you won't get the embedded hushd by default. You can either run an external
hushd, or compile hushd as well.


### Building on Linux


```
sudo apt-get install qt5-default qt5-qmake libqt5websockets5-dev qtcreator
git clone https://github.com/PirateNetwork/SevenSeas
cd SevenSeas
./build.sh
./sevenseas
```

### Building on Windows
You need Visual Studio 2017 (The free C++ Community Edition works just fine). 

From the VS Tools command prompt
```
git clone  https://github.com/PirateNetwork/SevenSeas
cd SevenSeas
c:\Qt5\bin\qmake.exe sevenseas.pro -spec win32-msvc CONFIG+=debug
nmake

debug\sevenseas.exe
```

To create the Visual Studio project files so you can compile and run from Visual Studio:
```
c:\Qt5\bin\qmake.exe sevenseas.pro -tp vc CONFIG+=debug
```

### Building on macOS

You need to install the Xcode app or the Xcode command line tools first, and then install Qt. 


```
git clone https://github.com/PirateNetwork/SevenSeas
cd SevenSeas
qmake sevenseas.pro CONFIG+=debug
make

./SevenSeas.app/Contents/MacOS/SevenSeas
```

### Support

For support or other questions, Join [Discord](https://pirate.black/discord), or [file an issue](https://github.com/PirateNetwork/SevenSeas/issues).
