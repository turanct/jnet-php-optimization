# Install and configure Apache JMeter

## Overview

1. [Install Apache JMeter](#install-apache-jmeter)
2. [Configure Apache JMeter](#configure-apache-jmeter)
3. [Resources](#resources)

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
1. Add a `Thread Group`: right click at "Test Plan", then click "Add" > "Threads (Users)" > "Thread Group".
2. Change the following parameters:

	Name: Jnet Test Case
	Number of Threads (users): 15 (= the number of individual "users")
	Ramp-Up Period (in seconds): 1 (= after which interval the next user requests will start)
	Loop Count: 2 (= how often will each user request a page)

3. In the next steps we will add 2 pages. This means one batch will request 2 pages x 15 users x 2 loops = 60 requests.
4. Add `HTTP Request Defaults`: right click at "Jnet Test Case", then click "Add" > "Config Element" > "HTTP Request Defaults".
5. Change the following parameters:

	Name: My Website
	Server Name or IP: www.mywebsite.com

6. Add a `HTTP Cookie Manager`: right click at "Jnet Test Case", then click "Add" > "Config Element" > "HTTP Cookie Manage".
7. Add a `HTTP Request`: right click at "Jnet Test Case", then click "Add" > "Sampler" > "HTTP Request".
8. Change the following parameters:

	Name: Homepage

9. Add a `HTTP Request`: right click at "Jnet Test Case", then click "Add" > "Sampler" > "HTTP Request".
10. Change the following parameters:

	Name: Subpage
	Path: /subpage

11. Add a `Graph Results` Listener: right click at "Jnet Test Case", then click "Add" > "Listener" > "Graph Results".
12. Save your project.
13. Test your setup by clicking on the Play button.

## 3. Resources
* [Apache JMeter Homepage](http://jmeter.apache.org)
* [Getting Started](http://jmeter.apache.org/usermanual/get-started.html)
* [Building a Web Test Plan](http://jmeter.apache.org/usermanual/build-web-test-plan.html)
* [Apache JMeter Blog](http://apache-jmeter.blogspot.be/)
* [Firing different requests in every iteration](http://stackoverflow.com/questions/8335649/jmeter-firing-different-requests-in-every-iteration)
