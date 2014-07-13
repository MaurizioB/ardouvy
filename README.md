ArdouVy
=======

ArdouVy is a remote controller for the Ardour DAW based on the Kivy library, 
and allows basic support for DAW operations via OSC support.
It was developed with musician needs in mind, so the user can stay in his 
place while playing his instrument and control what he/she needs to.
Please note that this is still a beta/debug release, intended just for testing
and still not complete. Don't yell at me, it's still a work in progress and,
much more important, I'm a musician, not a programmer :)

![alt text](jidesk.net/ardouvy/monitor-0.6.png "ArdouVy screenshot")


What does it do?
----------------

- List all the tracks/busses in the current section, with Mute/Solo toggles 
  and RecEnable for tracks;
- Control the main fader and [aux] sends of every track (see below);
- Transport control: go to start, play, stop, loop, rec enable, go to 
  next/previous marker, slider (playhead) positioning;

Requirements
------------

- Ardour version 3 (latest is better), version 2 supports only transport.
- Network connection. For smartphone/tablet devices you will probably use a 
  wireless network, and if you don't have one and your computer supports it, 
  you can share your wifi connection and use it for/from your device.
  Technically you should be able share your Android device connection with your
  computer, allowing you to still use your internet connection on your device.
  Keep in mind that this will obviously drain a lot of battery power.

How to make it work?
--------------------

Start a session in Ardour, go to Edit/Preferences, then Control Surfaces and 
enable both checkboxes for "Open Sound Control (OSC)".
Find the **local** ip address of the machine running Ardour ("ifconfig" command 
if you know how to use the command line, or check the network settings of your 
computer), it is usually something like "192.168.1.2".
Run ArdouVy on the computer/device. It will try to connect and probably fail, 
so open the preferences (standard menu button on Android, F1 on computers) and 
edit the ip address field, then close the preferences and then ArdouVy.
If everything is in place, at the next start, it will show the complete 
track/bus list, as it is listed in ardour.
To access the prev/next marker and slider locator, just click/tap on the small
button on the left of the main transport panel.

Faders
------

As default, ArdouVy will allow you to control the main volume fader for every 
track/bus.
It is possible to control the [aux] sends of every track, which is very useful
for musician monitoring while playing/recording.
Unfortunally the OSC support for this is still incomplete, and you will need 
to set it carefully on your Ardour session.
Every track that has a send *must* have it in the specific order of the busses 
in your track layout. Since the send gains are commanded using a simple number 
id, I have no way (yet) to know how many sends a track has and which are they.
Sometimes you have tracks without sends, others you may not need to send to
every bus, so just add the send and disable it.
For complex routing situation (e.g. a drumset bus) you'll have to think about 
the way they are ordered. I'm sorry for this, I'm in talks with Ardour 
maintainers and trying to persuade them to add a more complete OSC support.

Known bugs
----------

- Sleep mode makes the app close (get KeepScreen app on Google Play and add 
  ArdouVy to its list)
- Fader "listen" (changing fader gains on Ardour should reflect on ArdouVy)
  doesn't work yet, but it will ;)
- Fader values will not be remembered once the app is closed
- Transport slider sometimes acts weirdly when manually moving to a location
- Timeout option in settings actually does nothing yet :)
- Ip address in settings accepts almost everything, it's up to you.

Contact
-------

If you want to write me about problems, suggestions and (please, not too many)
complaints about ArdouVy, or just tell me the name of your cat or what you want
from Santa, you can contact me at maurizio.berti on gmail.
This app is free, I'll add a donation system, but if you want to support me in 
some way in the meantime, you can visit my (almost empty) website, listen to 
some of my music and give me your comments:

[http://jidesk.net]

Also, something more on SoundCloud:

[https://soundcloud.com/musicamante]

Thank you, and make good music! :)
