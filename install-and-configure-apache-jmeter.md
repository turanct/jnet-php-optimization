# Install and configure Apache JMeter

## Overview

1. Install Apache JMeter
2. Configure Apache JMeter
3. Resources

## 1. Install Apache JMeter
1. Download "apache-jmeter-2.8.tgz" or newer from http://jmeter.apache.org/download_jmeter.cgi and unpack the tarball.
2. Verify if you have a proper version of Java (JVM 1.5 or higher) installed (basic JRE edition won't work) by opening a Windows Prompt window:
	C:\>cd C:\Program Files\Java\jdk1.7.0_07\bin
	C:\Program Files\Java\jdk1.7.0_07\bin>java -version
	java version "1.7.0_07"
	Java(TM) SE Runtime Environment (build 1.7.0_07-b11)
	Java HotSpot(TM) 64-Bit Server VM (build 23.3-b01, mixed mode)
3. Try to start Apache JMeter by double clicking `apache-jmeter-2.8\bin\jmeter.bat`. If you get an `errorlevel=9009` error, you are not using JDK. If you get an error `Unrecognized VM option '+HeapDumpOnOutOfMemoryError' Could not create the Java virtual machine. errorlevel=1` then comment the next line in the `jmeter.bat` file:
	set DUMP=-XX:+HeapDumpOnOutOfMemoryError
After that the JMeter console should open successfully!

## 2. Configure Apache JMeter
**Coming soon**

## 3. Resources
* [Apache JMeter Homepage](http://jmeter.apache.org)
* [Getting Started](http://jmeter.apache.org/usermanual/get-started.html)
* [Building a Web Test Plan](http://jmeter.apache.org/usermanual/build-web-test-plan.html)
* [Apache JMeter Blog](http://apache-jmeter.blogspot.be/)
* [Firing different requests in every iteration](http://stackoverflow.com/questions/8335649/jmeter-firing-different-requests-in-every-iteration)
