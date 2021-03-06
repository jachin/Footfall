#Footfall

###Introduction

Footfall is a camera based people counting system that uses a  Raspberry Pi and Pi Cam. There is more information about the system on our [blog](http://blogs.wcode.org/2015/04/footfall-a-camera-based-people-counting-system-for-under-60/).

The source code provides a barebones system that will require some customisation. 

**Disclaimer**:
The original software was intended for sole use within Watershed, therefore some of the source code has been altered for public use and differs slightly to our systems. For example our system generated event tags showing screening in conjunction with the total number of people in Watershed, to do this we had to pre-populate some timestamps and may cause an issue if the system is ran past a certain time.

###How to Build
You will need a few extra packages to build the RPi application.
Copy the getrepos.sh file and place it inside the addons folder of your openFrameworks folder. Run the script by navigating to the addons folder and entering the following command into Terminal `./getrepos.sh`. This will pull down the require packages.

You will also need to update your Pi

`sudo apt-get update`

`sudo apt-get upgrade`

`sudo raspi-update`

Create a new app in openFrameworks, then copy the source code across.

**Make sure you add the required addons to the addons.make file**

Then build the app using the make command.

###How to Customise
Inside the bin/data folder of the RPi App there is a config.xml file. This contains all of the relevant variables you will need to change. 

Inside the <UPLOADURL> tag put your upload.php url this will fire the events into the database.
The other settings will need tweaking depending on where you place the tracker.

###Thanks
Thanks to Kyle McDonald for [ofxCv](http://github.com/kylemcdonald/ofxCv) and George Profenza for [ofxCvPiCam] (https://github.com/orgicus/ofxCvPiCam).