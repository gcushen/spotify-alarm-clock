# Spotify Rise

A lightweight alarm clock for the [Spotify Linux Client](https://www.spotify.com/download/linux/).

Features

* specify any Spotify track or album *(or playlist, with Spotify v0.9)* to wake up to
* shuffle mode support
* alarm fades in gradually
* alarm timeout in case you are on holiday or have a hangover :laughing:

Check out the [tutorial](https://georgecushen.com/spotify-alarm-clock-ubuntu-linux/) or see below for installation.


## Installation

Install the [Spotify Linux Client](https://www.spotify.com/download/linux/):

1. Add the Spotify repository signing key to be able to verify the download

        sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys BBEBDCB318AD50EC6865090613B00F1FD2C19886

2. Add the Spotify repository

        echo deb http://repository.spotify.com stable non-free | sudo tee /etc/apt/sources.list.d/spotify.list

3. Update the list of available packages

        sudo apt-get update

4. Install Spotify

        sudo apt-get install spotify-client

Start Spotify, signup/login, test audio playback, and then close it:

    spotify

Install an alarm scheduler and dependencies:

    sudo apt-get install alarm-clock-applet wmctrl xautomation
    
Install the Spotify Rise plugin:

    cd ~/Downloads/
    wget -O spotify-rise https://raw.githubusercontent.com/gcushen/spotify-rise/master/spotify-rise
    sudo install spotify-rise /usr/local/bin/spotify-rise

Open the alarm scheduler:

    alarm-clock-applet

And configure it to run the command `spotify-rise <URI>` where `<URI>` is the Spotify URI to play. Copy a *track* URI within an album by right clicking on a track, choosing *Copy Spotify URI*, and pasting it as the `<URI>` placeholder.

You may customize the `spotify-rise` command with the following options:

Option        | Function
:-------------| :-------
`-t`          | Toggle shuffle mode (if not already toggled in Spotify and you want shuffle mode)
`-s`          | Expect that shuffle mode is already active
`-h `         | Help 
`-c <cutoff>` | Override the default 15 minute alarm timeout. Units are minutes. A zero value removes the timeout.

Continue reading on to the section below for example usage.

To stop the alarm, you can either pause the current song in the Spotify Linux Client or over WiFi with the Spotify Mobile App, or just let the alarm automatically timeout after 15 minutes.

That's it, rise and shine in style with Spotify Rise! Remember to test your alarm and speakers have been setup correctly before relying on them to wake you up!

**Note:** Spotify **v1** no longer supports playing playlists/albums via Dbus, but we can partially workaround this issue by providing the URI of a (random) track within a desired album. For playlist support, currently you will need to downgrade to Spotify **v0.9**.


## Examples

Play an album/track, starting with specified track URI:

    spotify-rise spotify:track:0I2kwvXCLolYQ4nZQcF6EQ

Play an album in shuffle mode, assuming you keep Spotify in shuffle mode:

    spotify-rise -s spotify:track:0I2kwvXCLolYQ4nZQcF6EQ

Play an album in shuffle mode, assuming you do not keep Spotify in shuffle mode:

    spotify-rise -ts spotify:track:0I2kwvXCLolYQ4nZQcF6EQ


## Contributing

Please use the [issue tracker](https://github.com/gcushen/spotify-rise/issues) to report any bugs or feature requests, or alternatively make a pull request.


## License

Copyright 2016 [George Cushen](https://georgecushen.com).

Released under the [MIT](https://github.com/gcushen/spotify-rise/blob/master/LICENSE.md) license.
