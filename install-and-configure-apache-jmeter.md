# Install and configure Apache JMeter

## Overview

1. [Install Apache JMeter](#1-install-apache-jmeter)
2. [Configure Apache JMeter](#2-configure-apache-jmeter)
3. [Resources](#3-resources)

## 1. Install Apache JMeter
- Download "apache-jmeter-2.8.tgz" or newer from http://jmeter.apache.org/download_jmeter.cgi and unpack the tarball.
- Verify if you have a proper version of Java (JVM 1.5 or higher) installed (basic JRE edition won't work) by opening a Windows Prompt window:

code:
	C:\>cd C:\Program Files\Java\jdk1.7.0_07\bin
	C:\Program Files\Java\jdk1.7.0_07\bin>java -version
	java version "1.7.0_07"
	Java(TM) SE Runtime Environment (build 1.7.0_07-b11)
	Java HotSpot(TM) 64-Bit Server VM (build 23.3-b01, mixed mode)

- Try to start Apache JMeter by double clicking `apache-jmeter-2.8\bin\jmeter.bat`. If you get an `errorlevel=9009` error, you are not using JDK. If you get an error `Unrecognized VM option '+HeapDumpOnOutOfMemoryError' Could not create the Java virtual machine. errorlevel=1` then comment the next line in the `jmeter.bat` file:

jmeter.bat:
	set DUMP=-XX:+HeapDumpOnOutOfMemoryError

After that the JMeter console should open successfully!

## 2. Configure Apache JMeter
- Add a `Thread Group`: right click at "Test Plan", then click "Add" > "Threads (Users)" > "Thread Group".
- Change the following parameters:

parameters:
	Name: Jnet Test Case
	Number of Threads (users): 15 (= the number of individual "users")
	Ramp-Up Period (in seconds): 1 (= after which interval the next user requests will start)
	Loop Count: 2 (= how often will each user request a page)

- In the next steps we will add 2 pages. This means one batch will request 2 pages x 15 users x 2 loops = 60 requests.
- Add `HTTP Request Defaults`: right click at "Jnet Test Case", then click "Add" > "Config Element" > "HTTP Request Defaults".
- Change the following parameters:

parameters:
	Name: My Website
	Server Name or IP: www.mywebsite.com

- Add a `HTTP Cookie Manager`: right click at "Jnet Test Case", then click "Add" > "Config Element" > "HTTP Cookie Manage".
- Add a `HTTP Request`: right click at "Jnet Test Case", then click "Add" > "Sampler" > "HTTP Request".
- Change the following parameters:

parameters:
	Name: Homepage

- Add a `HTTP Request`: right click at "Jnet Test Case", then click "Add" > "Sampler" > "HTTP Request".
- Change the following parameters:

parameters
	Name: Subpage
	Path: /subpage

- Add a `Graph Results` Listener: right click at "Jnet Test Case", then click "Add" > "Listener" > "Graph Results".
- Save your project.
- Test your setup by clicking on the Play button.

## 3. Resources
* [Apache JMeter Homepage](http://jmeter.apache.org)
* [Getting Started](http://jmeter.apache.org/usermanual/get-started.html)
* [Building a Web Test Plan](http://jmeter.apache.org/usermanual/build-web-test-plan.html)
* [Apache JMeter Blog](http://apache-jmeter.blogspot.be/)
* [Firing different requests in every iteration](http://stackoverflow.com/questions/8335649/jmeter-firing-different-requests-in-every-iteration)
