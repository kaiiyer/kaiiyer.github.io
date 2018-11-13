---
layout: post
title: Setting up OpenCV with Python 2
---

The first time I tried to use OpenCV on my computer, I had to download the sources of lots of libraries and had to spend the next 12 hours figuring out how to compile them and then get the whole thing to work with Python. Thankfully, a person now trying to use OpenCV now does not have to go through the same ordeal. This is because, precompiled libraries called wheels are now available for easy installation of OpenCV. In this post, I will show you how.  

# Prerequisites  
First of all, make sure your distro is still supported. Linux distributions after the end of their release cycle usually do not allow installing softwares from repositories. That is, you would not be able to use your package manager to install software. So be sure to have a "recent" Linux distribution.  
Lets start by updating your list of packages  

    $ sudo apt-get update  

With this post, we are dealing with the Python 2 side of things. so make sure it is installed. On Debian derivatives, you can just do  

    $ sudo apt-get install python  

If you are on fedora,  
    
    $ sudo dnf install python27  

Once that is out of our way, we need to install the Python package manager, pip. On Debian derivatives, do  
    
    sudo apt-get install python-pip

On fedora, you can do
    
    $ sudo dnf install python-pip

Now we proceed to install Virtualenv.  

# Setting up Virtualenv  
Virtualenv is a container inside which you can set a Python environment complete with libraries which is independent from the rest of the system. Setting up Virtualenv is worth it, as it won't interfere with the rest of your system and will continue to work after a distro hop. Now that we have pip on our system, installating Virtualenv is as easy.

On fedora, do
    
    $ sudo dnf install python2-virtualenv 

If you are on Debian, do
    $ sudo apt-get install python-virtualenv

Once installed, go to someplace where you want to keep the files for your project. Create a directory for the same and initialize a virtualenv inside the directory. It is done as follows.  
    
    $ mkdir opencv  
    $ cd opencv  
    $ virtualenv . -p python2 

To make a virtualenv work for us, we need to activate it. This is done by calling the activate script.  
    
    $ source bin/activate  

Once this is properly done, your prompt should change to something that resembles  
    
    (opencv) $  

Okay. Thats it. Lets move on.  

# Installing the libraries
Now we address the elephant in the room. Let us setup OpenCV and some of the essential packages to make it work for us.  
    
    $ pip install opencv-contrib-python # the OpenCV package  
    $ pip install imutils               # convinience functions  
    $ pip install matplotlib            # easily plot the resultant images  
    $ pip install jupyter               # easy, powerful programming environment
    $ pip install numpy                 # for managing all those image arrays  

# Lets code!  
If you want an easy to use programming environment for learning OpenCV, you just installed it. We are ofcourse, talking about Jupyter Notebook. To start, do  

    (opencv) $ jupyter notebook  

Some easy examples can be found [here](https://github.com/karuvally/cv_workshop). Once you are done coding, you can quit by presssing "Ctrl + C", then deactivate Virtualenv by running "deactivate" command 

    (opencv) $ deactivate

