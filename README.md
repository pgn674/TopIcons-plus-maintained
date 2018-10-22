# TopIcons Plus Maintained

## Introduction

Many applications, such as chat clients, downloaders, and some media players, are meant to run long-term in the background even after you close their window. These applications remain accessible by adding an icon to the GNOME Shell Legacy Tray. However, the Legacy Tray is hidden until you push your mouse into the lower-left of the screen and click on the small tab that appears. TopIcons Plus Maintained brings all icons back to the top panel, so that it's easier to keep track of apps running in the backround.

Take a look at TopIcons Plus Maintained in action. Before installing (standard GNOME Legacy Tray in the bottom left):

![Before](https://raw.githubusercontent.com/pgn674/TopIcons-plus-maintained/master/screenshots/before.png)

After installing (icons have moved to the top right):

![After](https://raw.githubusercontent.com/pgn674/TopIcons-plus-maintained/master/screenshots/after.png)

You also get some options to control the look and feel. You can leave the icons in full color:

![Tray](https://raw.githubusercontent.com/pgn674/TopIcons-plus-maintained/master/screenshots/tray1.png)

Or dynamically convert them to grayscale:

![Tray](https://raw.githubusercontent.com/pgn674/TopIcons-plus-maintained/master/screenshots/tray2.png)

Enjoy!


## Installation

TopIcons Plus Maintained requires GNOME Shell 3.16 or newer, and has been tested up to 3.30.1.

### Get it from the extensions website

Once the extension is reviewed, you will be able to point your web browser to the TopIcons Plus Maintained page on the [GNOME Shell Extensions website](https://extensions.gnome.org/extension/1493/topicons-plus-maintained/). Until then, the preview page is available [here](https://extensions.gnome.org/review/8540).

GNOME uses a browser addon, which should have come with your Linux distro, to provide a web interface to the extensions manager on your system. Currently, only Firefox is supported, but support for other browsers is in the works. The first time you visit this website, you should be prompted to enable this browser addon -- [see the FAQs](https://extensions.gnome.org/about/#no-detection) if you have any issues, then go back to the TopIcons Plus Maintained page.

All you have to do next is click the switch on the extension page from off to on.

![Toggle Switch](https://raw.githubusercontent.com/pgn674/TopIcons-plus-maintained/master/screenshots/toggle-switch.png)

There will be a GNOME Shell pop-up asking you to confirm that you want to download and install this extension. After that, it may take a moment for the extension to set itself up, but *you* are done. Icons will move from the legacy tray to the top panel on their own.

If you want to tweak the icons' look and feel, you can go to the web page for [Installed Extensions](https://extensions.gnome.org/local/). Click on the wrench-and-screwdriver button to open the TopIcons Plus Maintained settings, or click the red X button to uninstall.

![Installed Extensions web page](https://raw.githubusercontent.com/pgn674/TopIcons-plus-maintained/master/screenshots/installed-extension-web-page.png)

If you install extensions from the GNOME website like this, be sure to revisit this page occasionally to check for updates (look for a green update button).

### Or compile it yourself

Pre-Requisite: You need the *make* utility :

```bash
# Debian, Ubuntu
sudo apt-get install make
# Red Hat, Fedora
sudo dnf install make
```

Download the code to any folder, using git:

```bash
git clone https://github.com/pgn674/TopIcons-plus-maintained.git
```

Go into the TopIcons Plus Maintained project directory and execute the installation script.

```bash
cd TopIcons-plus-maintained
make install
```

This will compile the glib schemas and copy all the necessary files to the GNOME Shell extensions directory for your own user account (so you don't need admin privileges to run `make`). By default, TopIcons Plus Maintained will live in the directory `~/.local/share/gnome-shell/extensions/TopIcons-plus-maintained@pgn674.com/`.

If you want to install the extension so that it will be usable system-wide, you'll have to change the `INSTALL_PATH` variable, and run as root.

```bash
sudo make install INSTALL_PATH=/usr/share/gnome-shell/extensions
```

Now, reload GNOME Shell. You can either hit <kbd>Alt</kbd>+<kbd>F2</kbd>, type `r`, and hit enter --- or login/logout.

![Reload Gnome](https://raw.githubusercontent.com/pgn674/TopIcons-plus-maintained/master/screenshots/reload.png)

Finally, launch the *gnome-tweak-tool* utility to manage extensions. There, you can enable *TopIcons Plus Maintained* and then tweak its look and feel.

![Enable TopIcons](https://raw.githubusercontent.com/pgn674/TopIcons-plus-maintained/master/screenshots/tweak.png)

## Known issues

GNOME Shell by default now runs on top of [Wayland](https://wayland.freedesktop.org/) by default, as of release 3.22. However, there are still some remaining bugs, as not all applications, particularly non-GNOME apps, have adapted to Wayland yet. These really have nothing to do with TopIcons Plus Maintained itself, but we do have a [GitHub Issue to keep track of workarounds](https://github.com/pgn674/TopIcons-plus-maintained/issues/47) while we wait for the different app developers to catch up with the new graphics backend.

## Credits

TopIcons Plus Maintained is a fork of TopIcons Plus by phocean, which itself was a fork of TopIcons. Many thanks go to Adel Gadllah for making the original extension, and also to Mjnaderi for the [Toptray fork](https://github.com/mjnaderi/TopTray).

Also, thanks to all contributors (code and issues), and especially to:

- [nevesnunes](https://github.com/nevesnunes) for the very nice code improvements he brought up,
- [terrycloth](https://github.com/terrycloth) for his contributions to the installation script and documentation to make it ready for the Fedora packaging.
