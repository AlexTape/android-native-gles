# android-native-gles
aka Angles

## Purpose
* Minimize time to triangle for Android game developers using the NDK and OpenGL ES 2.0
* Provide a correct and minimalistic (but complete) template with correctly sized placeholder icons etc.
* Support development on Windows, OS X and Linux

### Tested On
* Samsung Nexus S (4.1.2)
* Amazon Kindle Fire (~2.3)
* Asus Eee Pad Transformer Prime TF201 (4.1.1)
* Nvidia Shield (4.2.1)
* Samsung Galaxy Nexus (4.3)
* Samsung Galaxy S4 (4.2.2)

## Prerequisites
* Install the Android [SDK](http://developer.android.com/sdk/index.html) and [NDK](http://developer.android.com/tools/sdk/ndk/index.html)
* Setup environment variables and paths as instructed above (or insert instructions here, if necessary)

### OS X Mavericks
OS X Mavericks no longer provides Apache Ant and you must download and install it manually from [here](http://ant.apache.org/).

## Building

First, from the command line in the project root, create the build files using `android update project`. We are setting the build SDK version to 18 and giving our project the name Angles.

	android update project --path . --target android-18 --name Angles

Next, compile the native code

	ndk-build
	ndk-build V=1 -B (verbose, rebuild)

Build the package

	ant debug

Or build and install in one go

	ant debug install

Uninstalling

	ant uninstall

## Running

Start the Angles app on the device and hopefully there will be a triangle on the screen.

### Getting Log Output

Getting a list of the connected devices

	adb devices

Printing all the log output from the connected device

	adb shell logcat

If there are multiple connected devices, you may select one using -s as shown below

	adb -s <deviceid> shell logcat

To filter out log messages not belonging to the app at hand use -s \<tag\> like this

	adb -s <deviceid> shell logcat -s Angles

## TODO
* If possible, hide or dim "software buttons" (correct name?) on tablets
* Up the quality of the code
	* Make sure there are no leaks or other defects
	* Clean up the syntax / code convention
* Up the quality of this README
* Add support for Nvidia's Tegra Android Development Pack
