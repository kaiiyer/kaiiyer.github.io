---
layout: post
title: Setting up OpenCV with Python 3
---

Things change. Half an year ago, I was happy with running OpenCV on Python 2.
But not anymore. As hard as it is for me to admit, it is time to switch to
Python 3. So here is my supposedly easy to follow tutorial on setting up OpenCV
on Python 3.

# Prerequisites  
First of all, get the latest package listings from the repository. If you are
on fedora, you can safely skip this. If you are on Debian, do the following.

    $ sudo apt-get update

Lets make sure Python 3 and its dev libs are installed. If on Debian, run 

    $ sudo apt-get install python3 python3-dev

If you are on fedora,  
    
    $ sudo dnf install python3 python3-devel

Now, let us install the python package manager, more commonly called pip. On
Debian, you would want to do this,
    
    sudo apt-get install python3-pip

On fedora, you can do
    
    $ sudo dnf install python3-pip

Now we can proceed to install VirtualEnv. 

# Setting up Virtualenv  
Virtualenv is a container inside which you can set a Python environment complete
with libraries which is independent from the rest of the system. Setting up
Virtualenv is worth it, as it allows us to maintain multiple versions of
libraries parallely without conflicts. 

On fedora, do
    
    $ sudo dnf install python3-virtualenv 

If you are on Debian, do 

    $ sudo apt-get install python3-venv

Once installed, go to someplace where you want to keep the files for your
project. Create a directory for the same and initialize a virtualenv inside
the directory. It can be done as follows
    
    $ mkdir opencv 
    $ cd opencv 
    $ python3 -m venv .

To make a virtualenv work for us, we need to activate it. This is done by
calling the activate script.  
    
    $ source bin/activate  

Once this is properly done, your prompt should change to something that
resembles  
    
    (opencv) $  

That should do it. Let us install the libraries. 

# Installing the libraries
Now we address the elephant in the room. Let us setup OpenCV and some of the
essential packages to make it work for us. 
    
    $ pip install opencv-contrib-python # the OpenCV package  
    $ pip install imutils               # convinience functions  
    $ pip install matplotlib            # easily plot the resultant images  
    $ pip install jupyter               # easy, powerful programming environment
    $ pip install numpy                 # for managing all those image arrays  

# Lets code!  
If you want an easy to use programming environment for learning OpenCV, you just
installed it. We are ofcourse, talking about Jupyter Notebook. To start, do  

    (opencv) $ jupyter notebook  

As always, once you are done coding, you can quit by presssing "Ctrl + C", then
deactivate Virtualenv by running "deactivate" command 

    (opencv) $ deactivate

