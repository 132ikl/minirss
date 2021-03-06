# minirss: a minuscule RSS notifier

minirss is a tiny shell script to help you keep track of your RSS feeds. Whenever one of your feeds updates, you'll get a notification. Simply middle click (or whatever your configured action button is) and you will be taken to the link. minirss is just over 100 lines of bash.

Dependencies:
* xmlstarlet
* bash >= 4.0
* `notify-send` OR `dunstify`
* xdg-open

## Installation

On Arch Linux, minirss can be installed using its [AUR package](https://aur.archlinux.org/packages/minirss-git/).

You can also manually install minirss through this process:
```
sudo cp minirss /usr/bin/minirss
cp minirss ~/.config/systemd/user/
systemctl --user enable --now minirss
```

## Setup

minirss uses two files: a config file (default in $XDG_CONFIG_HOME) and a storage file (default in $XDG_DATA_HOME). To add feeds to watch, simply add a line with the feed's URL in the config file. Optionally, to add a display name simply add the name with a `|` character between the name and the url, ex:
```
my cool display name|https://link-to-cool-rss-feed.com/feed.xml
```

You can change the path of both of these files and the delay between checking feeds using the command line parameters (see `--help` for more info). minirss will also always use the most updated config, no need to restart.
