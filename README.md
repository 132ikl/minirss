# minirss: a minuscule RSS notifier

minirss is a tiny Python script to help you keep track of your RSS feeds. Whenever one of your feeds updates, you'll get a notification. Additionally, if you use dunst, simply middle click (or whatever your configured action button is) and you will be taken to the link.

## Installation

On Arch Linux, minirss can be installed using its [AUR package](https://aur.archlinux.org/packages/minirss-git/).

Dependencies (probably installable as `python-<name>` in your distribution):
* appdirs
* requests
* feedparser

You can also manually install minirss through this process:
```
sudo cp minirss /usr/bin/minirss
cp minirss ~/.config/systemd/user/
systemctl --user enable --now minirss
```

## Config

minirss uses two files: a config file (default in $XDG_CONFIG_HOME) and a storage file (default in $XDG_DATA_HOME). Each line has three `|` separate fields: name, url, and (optional) options field:
```
my cool display name|https://link-to-cool-rss-feed.com/feed.xml
cool feed with options|https://link-to-cool-rss-feed.com/feed.xml|options
```

minirss will also always use the most updated config, no need to restart.

## Feed Options

* `fullhistory`
    - Use this for non-chronological feeds (ie. the first entry in the feed is not the latest)

