# Official Gude for RHEL 8 VirtualBox Quick Install
https://developers.redhat.com/rhel8/install-rhel8-vbox

# Alternate Way to install VirtualBox Guest Additions on Fedora 32/31, CentOS/RHEL 8/7/6/5:
https://www.if-not-true-then-false.com/2010/install-virtualbox-guest-additions-on-fedora-centos-red-hat-rhel/

        
## Step by step with only essential steps:
[Assuming you already have virtualization software(like Oracle VirtualBox (https://www.virtualbox.org/)) installed on your host system]

1. Download RHEL ISO DVD Image from this link.
https://developers.redhat.com/products/rhel/download

2. Log in to your Red Hat account using "Red Hat login or email" option
   
   OR
   create a new account using "Don't have an account? Create one now."

   OR
   You can sign in by using any one of the Social media accounts like GitHub, StackOverflow, LinkedIn, Twitter, Facebook, Google or Microsoft Account

3. Create a new Virtual Guest Machine for RHEL with minimum 2GB RAM, 50GB ROM, 2 processors. 

4. Install the RHEL software using the instructions as per link: https://developers.redhat.com/rhel8/install-rhel8-vbox

5. Once installed and you are in you have to run below commands(script) inside the OS or using SSH connectio from outside.

    $sudo yum update
    $reboot

    $sudo yum groupinstall "Development Tools"
    $sudo yum install kernel-devel elfutils-libelf-devel
    
    $su -
        ## OR ##
    $sudo -i
    
    ## Fedora 32/31/30/29/28/27/26/25 and CentOS 8 / RHEL 8 ##
    $sudo dnf update kernel*

    ## CentOS/RHEL 7/6/5 ##
    $yum update kernel*
    $reboot

    ## CentOS 8 and Red Hat (RHEL) 8 ##
    $dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm

    ## CentOS/RHEL 8/7/6/5 ##
    $yum install gcc kernel-devel kernel-headers dkms make bzip2 perl

    ## Current running kernel on Fedora 32/31/30/29/28/27/26/25, CentOS 8/7/6 and Red Hat (RHEL) 8/7/6 ##
    $KERN_DIR=/usr/src/kernels/`uname -r`
    
    ## Export KERN_DIR ##
    $export KERN_DIR

    # Install VMBox Gues Additions directly (using insert and run option) or by using mount after isert
    $mkdir /media/VirtualBoxGuestAdditions
    $mount -r /dev/cdrom /media/VirtualBoxGuestAdditions
    $cd /media/VirtualBoxGuestAdditions

    # Then run following command
    $./VBoxLinuxAdditions.run








