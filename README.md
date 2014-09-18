Spotify Rise
============

This program provides a lightweight alarm clock for the [Spotify Linux client](http://www.spotify.com/us/download/previews/).

Installation
------------

Install the dependencies:

    $ sudo apt-get install wmctrl xautomation
    
Install the Spotify Rise alarm clock:

    $ cd ~/Downloads/
    $ sudo install spotify-rise.sh /usr/local/bin/spotify-rise.sh

Setup the alarm:

    $ EDITOR=gedit crontab -e

Add the following lines and save the file:

    #m hr dom mon dow command
    30 07 * * 1-5 /usr/local/bin/spotify-rise -s
This alarm will start at 07:30 Monday to Friday. To modify the alarm time, simply edit the first two values for minutes and hour respectively. For more advanced alarm setups, refer to the crontab manual for guidance.

That's it! Rise and Shine in style with Spotify-Rise and remember to test your alarm has been setup correctly before relying on it to wake you up!

## Options
    -u URI      play Spotify URI (playlist, album, etc.) - click 'Copy Spotify URI' within Spotify and paste as the URI parameter.
    -s			shuffle mode
    -t			toggle shuffle (if not already toggled and you want shuffle mode)

Copyright
---------

Spotify-Rise was created by George Cushen and is copyright (c) 2014. It is licensed under the GNU GPL v3 license - refer to the LICENSE file for details.

Feedback
--------

Bugs and feedback can be reported on [Github](https://github.com/neutreno/spotify-rise/issues).
