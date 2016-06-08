# Spotify Rise

A lightweight alarm clock for the [Spotify Linux Client](https://www.spotify.com/download/linux/).

Features

* specify any Spotify URI (track, playlist, album, etc.) to wake up to
* shuffle mode support
* alarm fades in gradually
* alarm timeout in case you are not in or have a hangover :laughing:

## Prerequisites

Install the [Spotify Linux Client](https://www.spotify.com/download/linux/) on your Raspberry Pi or Ubuntu computer:

```
# 1. Add the Spotify repository signing key to be able to verify downloaded packages
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys BBEBDCB318AD50EC6865090613B00F1FD2C19886

# 2. Add the Spotify repository
echo deb http://repository.spotify.com stable non-free | sudo tee /etc/apt/sources.list.d/spotify.list

# 3. Update list of available packages
sudo apt-get update

# 4. Install Spotify
sudo apt-get install spotify-client
```

## Installation

Install an alarm scheduler and dependencies:

    $ sudo apt-get install alarm-clock-applet wmctrl xautomation
    
Install the Spotify Rise alarm app:

    $ cd ~/Downloads/
    $ wget -O spotify-rise https://raw.githubusercontent.com/gcushen/spotify-rise/master/spotify-rise
    $ sudo install spotify-rise /usr/local/bin/spotify-rise

Schedule the alarm and configure it to run the command `spotify-rise`:

    $ alarm-clock-applet

You may customize the `spotify-rise` command with the following options:

Option     | Function
:----------| :-----
`-t`       | Toggle shuffle mode (if not already toggled in Spotify and you want shuffle mode)
`-s`       | Expect that shuffle mode is active
`-u <URI>` | Play a specific Spotify URI (track, playlist, album, etc.) - right click in Spotify and choose 'Copy Spotify URI' and paste it as the URI parameter.

That's it! Rise and shine in style with Spotify-Rise and remember to test your alarm has been setup correctly before relying on it to wake you up!

## Contributing

Please use the [issue tracker](https://github.com/gcushen/spotify-rise/issues) to report any bugs or feature requests, or alternatively make a pull request.

## License

Copyright 2016 [George Cushen](https://georgecushen.com).

Released under the [MIT](https://github.com/gcushen/spotify-rise/blob/master/LICENSE.md) license.
