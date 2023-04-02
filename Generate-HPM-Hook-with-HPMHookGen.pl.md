# Generate HPM Hook on windows

First you need to download and install Doxygen and Perl.

Doxygen: http://www.stack.nl/~dimitri/doxygen/download.html

Perl: http://www.activestate.com/activeperl/downloads


1. Run "Doxygen GUI frontend"

2. Click on "File" -> "Open"

3. Go on your Hercules folder -> "tools" -> "HPMHookGen" and select "doxygen.conf"

4. Now in the interface you will see Run, go on it.

5. Just click on "Run doxygen" and just close it.

6. Go on the "HPMHookGen" folder then run HPMHookGen.pl

# Generate HPM Hook on Linux

## Preparations (First Time)

First you have to install Doxygen and Perl. On Debian (Ubuntu) that may be achieved with:
```
sudo apt-get install doxygen
sudo apt-get install perl
```

After that, open a terminal at your Hercules root folder and run configure
```
./configure
```
**note**: This is required to be done once after you install Doxygen and Perl so `make` recognizes that they are installed.

## Generating HPM Hook

1. Change directories to **tools/HPMHookGen/** folder
```
cd tools/HPMHookGen/
```

2. Run `make`
```
make
```

HPM Hooks will be generated.

## Troubleshooting: `Can't locate XML/Simple.pm in @INC`

In case you have the error saying that it can't locate `XML/Simple.pm`, you should install `libxml-simple-perl`. On Debian/Ubuntu, you may run:
```
sudo apt-get install libxml-simple-perl
```

Once it installs, you can try running `make` again and it should work.