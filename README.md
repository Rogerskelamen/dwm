dwm - dynamic window manager
============================
dwm is an extremely fast, small, and dynamic window manager for X.


Requirements
------------
In order to build dwm you need the Xlib header files.


Installation
------------
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

    make clean install


Running dwm
-----------
Add the following line to your .xinitrc to start dwm using startx:

    exec dwm

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm


Configuration
-------------
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.

## More features
If you want to add new features to dwm, you can use some patches in [dwm official website](https://dwm.suckless.org/patches/). Every patches I used are stored in the fold `/patches`

There is something useful:
autostart   -- auto execute some scripts or applications once dwm start
vanitygaps  -- like i3-gaps, but dwm
fullscreen  -- fullscreen one window
noborder    -- do not show border
viewontag   -- follow a window to the tag it is being moved to
hide-vacant-tags -- hide any tag if it has no window
awesomebar  -- shows all tasks in the current tag in the taskbar at all times
status2d    -- allows colors and rectangle drawing in your DWM status bar
tatami      -- another layout
dwmc        -- allow us change dwm source code and take effect immediately

These two patches conflicts with each other:
systray     -- for application deamon icon display
alpha       -- make transparent for status bar
If you have to patch them both, use [this patch in github](https://github.com/bakkeby/patches/blob/master/dwm/dwm-alpha-systray-6.3_full.diff)
