st - simple terminal
--------------------
st is a simple terminal emulator for X which sucks less.  Gian's edit.

Applied patches:
--------------
 * st-scrollback-mouse-altscreen-20191024-a2c479c.diff
 * st-scrollback-mouse-20191024-a2c479c.diff
 * st-scrollback-20190331-21367a0.diff
 * st-xresources-20190105-3be4cf1.diff
 * st-selectioncolors-0.8.2.diff
 * st-openclipboard-20190202-3be4cf1.diff
 * st-copyurl-20190202-3be4cf1.diff
 * st-alpha-0.8.2.diff
 * st-anysize-0.8.1.diff
 * st-boxdraw_v2-0.8.2.diff
 * st-externalpipe-0.8.2.diff
 * st-externalpipe-signal-0.8.2.diff


External Pipe
------
Reading and writing st's screen through a pipe.

External Pipe signal
------
Run an externalpipe command upon receiving the SIGUSR1 signal. This is helpful for supporting externalpipe scripts which work across multiple st instances.

Anysize
-------
This patch allows st to resize to any pixel size, makes the inner border size dynamic, and centers the content of the terminal so that the left/right and top/bottom borders are balanced.

Boxdraw
--------
Custom rendering of lines/blocks/braille characters for gapless alignment.

ScrollBack
---------
allow scrollback using mouse wheel

Xresources
----------
allow parameters to be set from Xresources (including alpha and selectionbg)

SelectionColors
----------
Same selection color background (foreground remains the same)

OpenClipboard (open copied url)
------------
Mod+o to open whats in the clipboard selection

CopyUrl
------------
Select and copy the last URL displayed with Mod1+l. Multiple invocations cycle through the available URLs.

Alpha
-----------
Allows transparency. Can be set in the alpha parameter that can also be set in Xresources.

Requirements
------------
In order to build st you need the Xlib header files.

Installation
------------
Edit config.mk to match your local setup (st is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install st (if
necessary as root):
Remember to delete config.h (or backup it whatever) before trying out new patches

    make clean install


Running st
----------
If you did not install st with make clean install, you must compile
the st terminfo entry with the following command:

    tic -sx st.info

See the man page for additional details.

Credits
-------
Based on Aurélien APTEL <aurelien dot aptel at gmail dot com> bt source code.

