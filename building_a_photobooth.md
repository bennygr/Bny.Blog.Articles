<!--
Title:"Building a photo booth with a raspberry pi",
Date:"2014-05-14T22:13+0200",
Tags:"$TAGS",
PreviewLength:"500",
PreviewCode:"pb"
-->

This are just a few notes about my own approach for building a party photo booth using a raspberry pi.

<img src="http://raw.githubusercontent.com/bennygr/cheesecake/master/first_image.jpg" alt="img grab a prob & strike a pose" heigth="500" width="500" />

###Requirements

Key points of the photo booth:
- Single light source (just a common flash for your camera)
- Displaying new pictures directly on a computer screen or TV and show older pictures in an endless slide show.

###Building a booth
The booth itself was built based on Mark Wallace's [tutorial](http://www.youtube.com/watch?v=qLkHWtdPhis) except that I made my booth based on wood and used a bunch of common thermal blankets from a first aid kit as a reflector for the flash.

###Photo hardware 
- Camera
- Tripod
- Flash
- Wireless remote trigger 

###Electronic Hardware
- Raspberry PI + SD CARD + HDMI cable
- Computer screen or TV

###Software
Because I want to grab the photos from the camera and display them on the screen I wrote my own simple piece of software called [cheesecake](https://github.com/bennygr/cheesecake) to do this job. It is written in C++ using the Qt toolkit.

###Additional Stuff
- Some cool props can be found on [http://ohhappyday.com](http://ohhappyday.com/2011/05/photobooth-props-diy-and-free-printable-2)
- You will need enough batteries for the flash and the remote trigger!
- It is also suitable to have some additional thermal blankets, just for the case they get perforated.

###Raspberry PI configuration				

#####Autostart 

Starting cheesecake automatically 

	sudo vi /etc/xdg/lxsession/LXDE/autostart	
	@path to a script which starts cheesecake with your desired parameters

#####Disabling gvfs  
We need to disable gvfs to prevent it to block access to be camera. Remove the following files:

/usr/share/dbus-1/services/org.gtk.Private.GPhoto2VolumeMonitor.service
/usr/share/gvfs/mounts/gphoto2.mount
/usr/share/gvfs/remote-volume-monitors/gphoto2.monitor
/usr/lib/gvfs/gvfs-gphoto2-volume-monitor
				

#####Disable monitor sleep
Preventing the monitor to fall asleep

Adding the following line to the SeatDefault section of the lightdm config file  /etc/lightdm/lightdm.conf

	xserver-command=X -s 0 -dpms
