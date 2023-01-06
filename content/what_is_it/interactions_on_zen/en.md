# Interactions on Zen

**TL;DR: It’s a compositor and a protocol for an XR windowing system built on top of Wayland.**

If you understand the above, please jump to **Z Window System core concepts**. Otherwise, stay with us.


## What is a windowing system?

The windowing system is a framework that works on top of an OS. It displays the contents of apps on the screen. You use it every day, but you might not be aware since modern OS (like Windows, macOS, Ubuntu) comes with one by default. The windowing system is a concept from everyday 2D OS you are familiar with. It was not originally related to VR, but we adopted it.

For a windowing system to work, at least three components must exist; **client apps, a compositor, and a protocol.**

**Client apps** are the apps you use on GUI, like Google Chrome, Blender, or File Explorer.

**A compositor** is a program that communicates with client apps, listens for the content the apps want to show, and displays them into screens as overlapping windows. It also takes care of the windows' placement, how they are stacked, and which is active. So when you casually refer to "OS," often what you want to mean is "compositor." However, the compositor is not technically a part of the OS; it can be swapped in Linux operating systems (although it is fixed to the default one on Windows and macOS). While a compositor only takes care of visual aspects, the actual OS provides computational resources and foundations to the apps.

Finally, **a protocol** is a language in which the client apps and a compositor talk. Think of it like HTTP on the web; the server and your browser talk in HTTP.


![alt_text](images/image1.png "image_tooltip")


Your OS must have the above software. For example, on Ubuntu with Wayland protocol, it looks like this:

![alt_text](images/image2.png "image_tooltip")



## Z Window System core concepts

To realize an XR windowing system, we built **ZIGEN** (a protocol) and **Zen** (a compositor).

![alt_text](images/image3.png "image_tooltip")


ZIGEN is a protocol. Zen does all the actual work, including communication with 2D Wayland apps. **So if you want to try out our windowing system, Zen is what you should install.** You can switch your compositor easily; you can keep your existing OS (Ubuntu/Arch Linux).

Since ZIGEN is open-sourced, you can build 3D apps compatible with ZIGEN or develop another compositor which works like Zen.