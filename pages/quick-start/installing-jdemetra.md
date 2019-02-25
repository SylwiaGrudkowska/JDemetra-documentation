---
layout: left-menu
title: Installing JDemetra+
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
JDemetra+ is a stand-alone application packed in a zip package. To run JDemetra+ the Java RE 8 or higher is needed. Java RE can be 
downloaded from [Oracle website](https://www.oracle.com/technetwork/java/javase/downloads/index.html).

The official release of JDemetra+ is accessible at 
[a dedicated Github page](https://github.com/jdemetra/jdemetra-app/releases). The site presents all available releases - both official releases (labelled in green as latest releases) and pre-releases (labelled in red) - 
packed in zip packages. From the *Latest release* section either choose 
the installer appropriate for your operating system (Windows, Linux, 
Mac OS, Solaris) or take the portable zip-file. The installation process 
is straightforward and intuitive. For example, when the zip-file is 
chosen and downloaded, then under Windows OS the application can be found 
in the "bin"-folder of the installation/unpacked zip. To open an 
application, double click on nbdemetra.exe or nbdemetra64.exe depending 
on the system version (nbdemetra.exe for the 32-bit system version and 
nbdemetra64.exe for the 64-bit system version).

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/quick-start/RunningJDemetra.jpg)

{: .text-center.small}

**Launching JDemetra+**

If the launching of JDemetra+ fails, you can try the following
operations:

-   Check if Java SE Runtime Environment (JRE) is properly installed by typing in the following command in a terminal: *java --version*

-   Check the logs in your home directory:

    -   %appdata%/.nbdemetra/dev/var/log/ for Windows;

    -   \~/.nbdemetra/dev/var/log/ for Linux and Solaris;

    -   \~/Library/Application Support/.nbdemetra/dev/var/log/ for Mac OS X.

In order to remove a previously installed JDemetra+ version, the user
should delete an appropriate JDemetra+ folder.

### Running JDemetra+ {#running-jdemetra}

To open an application, navigate to the destination folder and double
click on *nbdemetra.exe* or *nbdemetra64.exe* depending on the system
version (*nbdemetra.exe* for the 32-bit system version and
*nbdemetra64.exe* for the 64-bit system version).

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref1.jpg)

{: .text-center.small}

**Running JDemetra+**

### Closing JDemetra+ {#closing-jdemetra}

To close the application, select *File → Exit* from the [File menu](http://localhost:4000/pages/reference-manual/file.html).

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref2.jpg)

{: .text-center.small}


**Closing JDemetra+**

The other way is to click on the close box in the upper right-hand
corner of the JDemetra+ window. If there is any unsaved work, JDemetra+
will display a warning and provide the user with the opportunity to save
it. The message box is shown below.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref3.jpg)

{: .text-center.small}

**The warning from leaving JDemetra+ without saving the workspace**