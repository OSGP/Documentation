# Vagrant

## Installation

This document describes the automatic installation procedure for your Open Smart Grid Platform development environment.

### Manual installation

If you would like to follow the **manual installation procedure**, please proceed to the [Manual Installation Chapter](manualinstallation.md).

### Overview

**Creating a Virtual Machine using Virtual Box and Vagrant**

To improve the usability of the Installation process, a Vagrant file and some puppet scripts are used to automatically set-up an virtual Open Smart Grid Platform development environment. The following steps will describe how to install VirtualBox, Vagrant and kick off the procedure by running the `vagrant up` command.

### System Requirements

The following system requirements are recommended:

* Core i5/i7 ~2.5GHz Dual Core, Quad Core recommended
* At least 16 GB RAM, 32 GB RAM recommended
* At least 20 GB free space, 50 GB free space recommended

The installation procedure has been tested on Windows 10.

### Install Vagrant and VirtualBox

Start by downloading VirtualBox by going to [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads) And follow the installation steps.

> **note:** If you already have VirtualBox, make sure it is at least **version 6.1.38**

![alt text](../../../.gitbook/assets/01.png)

> **note:** Check whether Virtualbox stores the images on a drive with enough free space. \(Open Oracle VM VirtualBox Manager -&gt; Preferences -&gt; General -&gt; Default Machine Folder\).

Now download and install Vagrant. Vagrant is available at the following URL: [https://www.vagrantup.com/downloads.html](https://www.vagrantup.com/downloads.html)

![alt text](../../../.gitbook/assets/02.png)

> **note:** If you already have Vagrant, make sure it is at least **version 2.3.0** Complete the installation and restart your PC.
>
> **note:** If you did a fresh install of Vagrant and already had a command prompt open, make sure you close this command prompt and open it again.

#### Tip

* Remember to enable Virtualization in your system BIOS.
* Also disable Hyper-V in Windows \(can be found in Windows Features\)

## Download and run the Vagrant file

First create a new directory \(for example: `D:\My Vagrant Images\OSGP Development\`\)

Browse to [https://github.com/OSGP/Config/tree/development/vagrant](https://github.com/OSGP/Config/tree/development/vagrant) and save the png image and Vagrantfile files in your newly created directory.

![alt text](../../../.gitbook/assets/03.png)

#### Note

* Make sure that the file is named like this: `Vagrantfile`  _without_ an extension!
* If the file has an extension \(for example .txt\) you can rename the file using the following console command.

  MacOS/Linux:

  ```text
  mv Vagrantfile.txt Vagrantfile
  ```

  Windows:

  ```text
  move Vagrantfile.txt Vagrantfile
  ```

Now open a Command Prompt and navigate to the newly created directory where you just put the files. Make sure that you run the Command Prompt using administrator rights.

> **note:** When you open the Vagrantfile you see that default the image is configured to run in virtualbox with 2 cpu cores and 8192 MB of RAM. If you need to you can change this to more or less cpu cores and RAM, but it is recommended to use the provided settings.

Run the following command: `vagrant up`

> **note:** In case of error bad uri Images/OSGP Development/hashicorp/itc/itc-ubuntu-mate-20.04-amd64  then use the following command;
>
> * vagrant destroy
> * vagrant box add itc/itc-ubuntu-mate-20.04-amd64
> * vagrant up
>
> **note:** In case of an error complaining about not being able to resolve a URL \(for instance to github.com\) then try using a different internet connection not behind a proxy.

![alt text](../../../.gitbook/assets/04.png)

Vagrant will now automatically download an Ubuntu image \(+- 2.6 Gb\), create a virtualbox image from it and run the installation puppet script when finished. This might take a while, depending on your internet speed. After some time \(while the script is still running\) you will notice that a window with an Ubuntu Virtual Machine pops-up. Don't log in yet, wait until the script in the Console is finished.

![alt text](../../../.gitbook/assets/05.png)

#### Tip

* If the script fails for some reason \(eg. Errors in the console such as time outs during downloading\), you can retry the procedure by running the following command `vagrant destroy && vagrant up`

Now that the script has ran its course, it will automatically log in on the Ubuntu virtual machine as user _dev_.

> **note:** For some actions, like `sudo`, you will have to enter the password of user _dev_. The password for user _dev_ is _dev_.

## Optimize your Open Smart Grid Platform Development virtualbox image.

At this point you also can adjust the virtualbox settings like cpus and memory size. If you don't want to adjust this proceed to Chapter 2.1.2. Platform Setup.

If you do want to update the virtualbox settings for this image, shut down the image first:

![alt text](../../../.gitbook/assets/06.png)

Once the machine has been Shut Down, open VirtualBox and right click on the new virtual machine \(called "OSGP Development"\) and select Settings. Go to System and increase the Base Memory of the system to at least 6144 MB \(6 GB\) \(or the maximum recommended \(in green\) amount for your system\).

![alt text](../../../.gitbook/assets/07.png)

Now go to the Processor Tab and increase the amount of Processors to the maximum recommended \(in green\) amount.

![alt text](../../../.gitbook/assets/08.png)

Close the Settings window and Start the Virtual Machine again. Once it is booted, you should be automatically logged in as the 'dev' user.

## Post actions

In order to use git correctly you need to execute the following commands in a terminal:

```text
git config --global user.name "your full name"
git config --global user.email yourEmailAddress
```

## Recap

You just created a virtual machine running Ubuntu with pre-installed tooling. Proceed with [Platform Setup](../setuposgp.md) of the guide describing how to set-up the open smart grid platform.

