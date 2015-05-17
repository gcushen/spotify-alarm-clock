Spotify Rise
============

This program provides a lightweight alarm clock interface for the [Spotify Linux client](http://www.spotify.com/us/download/previews/).

Features
* specify any Spotify URI (playlist, album, etc.) to wake up to
* shuffle mode support
* alarm fades in gradually
* alarm timeout in case you are not in or have a hangover :P

Installation
------------

Install an alarm scheduler and dependencies:

    $ sudo apt-get install alarm-clock-applet wmctrl xautomation
    
Install the Spotify Rise alarm app:

    $ cd ~/Downloads/
    $ wget -O spotify-rise https://raw.githubusercontent.com/gcushen/spotify-rise/master/spotify-rise
    $ sudo install spotify-rise /usr/local/bin/spotify-rise

Schedule the alarm and configure it to run the command `spotify-rise`:

    $ alarm-clock-applet

That's it! Rise and shine in style with Spotify-Rise and remember to test your alarm has been setup correctly before relying on it to wake you up!

Note: tested on Ubuntu 14.04 - 15.04.

### Options

**-u URI** : play a specific Spotify URI (playlist, album, etc.) - click 'Copy Spotify URI' within Spotify and paste as the URI parameter.

**-s**	: shuffle mode

**-t**	: toggle shuffle (if not already toggled and you want shuffle mode)

Copyright
---------

Spotify-Rise was created by George Cushen and is copyright (c) 2014. It is licensed under the GNU GPL v3 license - refer to the LICENSE file for details.

Feedback
--------

Bugs and feedback can be reported on [Github](https://github.com/gcushen/spotify-rise/issues).
