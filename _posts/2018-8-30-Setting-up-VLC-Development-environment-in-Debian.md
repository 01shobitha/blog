---
layout: post
title: Setting Up VLC Development Environment In Debian
published: true
permalink: /:title
---
Before setting up the development environment, let’s get to know why you should prefer VLC over other media players, why it’s the best, its cool features and a lot more!

## Play a video or audio from terminal:
You can play the audio/video by running a command in the terminal:

`$ vlc <path to the file>`


## Play  a youtube video in VLC:
Now let’s see how you can download a youtube video using VLC. Follow the above steps. Then,
1. While the video is playing, press ctrl+j to open the Codec box.
2. Then find an option called location and you can see a string. Copy the whole string and paste in your web browser and click enter.
3. You will see a downward arrow in the bottom right. Click on it and Voila! Your video is getting downloaded!

## Playback your desktop:
You can record desktop screen using VLC media player. Lets see how you can do it.
1. Open VLC and click on media.
2. Click on Open Capture Device.
3. Now, click on the capture device tab and select Desktop from the Capture mode drop down box.
4. Now go down and set the frame rate to 15 frames per second.
5. Click the down arrow next to the Play button and select Convert.
6. The convert box will open up.  Now go to the profile section and choose what you need.
7. Now add your destination file by clicking on the browse option.
8. Click on start to start recording.
9. Click on the stop button to stop recording.

## Setting it up:
I had referred to this <a href= "https://wiki.videolan.org/Compile_VLC/">link</a> I will be mostly mentioning about the commands mentioned there. So let us begin.

**1. To get the GNU build system:**


{% highlight js %}
sudo apt-get install git build-essential pkg-config libtool automake autopoint gettext
{% endhighlight %}

**2. Get the source code:**

* Clone it
{% highlight js %}
git clone https://github.com/videolan/vlc.git
{% endhighlight %}
* Get into the directory
{% highlight js %}
cd vlc
{% endhighlight %}
* <a href="https://stackoverflow.com/questions/1254542/what-is-bootstrapping">Bootstrap</a> the source tree
{% highlight js %}
./bootstrap
{% endhighlight %}

**3. Get all the needed libraries**
* First update your package lists using:
{% highlight js %}
sudo apt-get update
{% endhighlight %}
* Then get the required libraries:
{% highlight js %}
sudo apt-get build-dep vlc
{% endhighlight %}

**4. Check whether your system is able to compile VLC**
{% highlight js %}
./configure
{% endhighlight %}

This step might give you the following error:

` configure: error: No package 'xcb-xkb' found. Pass --disable-xcb to skip X11 support.`

**Don’t** disable xcb. Instead install it. Find the required package for your system and then install it using a package manager. I used aptitude.

* Install aptitude using:
{% highlight js %}
sudo apt-get install aptitude
{% endhighlight %}

* Now, search package using:
{% highlight js %}
aptitude search xcb
{% endhighlight %}

* After you find it, install it by running (below is the package I needed, you need to find for your distribution) :
{% highlight js %}
sudo aptitude install libxcb-xkb-dev
{% endhighlight %}

* Run the command again:
{% highlight js %}
./configure
{% endhighlight %}

**5. Now compile  :**
{% highlight js %}
make
{% endhighlight %}

**6. Run it :**
{% highlight js %}
./vlc
{% endhighlight %}

**7. Now install XCB libraries by running :**
{% highlight js %}
sudo apt-get install libxcb-shm0-dev libxcb-xv0-dev libxcb-keysyms1-dev libxcb-randr0-dev libxcb-composite0-dev
{% endhighlight %}

## That's it. You are good to go :)