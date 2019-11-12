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
 * st-keyboard_select-0.8.2.diff
 * st-copyurl-20190202-3be4cf1.diff
 * st-alpha-0.8.2.diff

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

Keyboard Select
-----------
When you run "keyboard_select", you have 3 modes available :

* move mode : to set the start of the selection;
* select mode : to activate and set the end of the selection;
* input mode : to enter the search criteria.

Shortcuts for move and select modes :

 * h, j, k, l:    move cursor left/down/up/right (also with arrow keys)
 * !, _, *:       move cursor to the middle of the line/column/screen
 * Backspace, $:  move cursor to the beginning/end of the line
 * PgUp, PgDown : move cursor to the beginning/end of the column
 * Home, End:     move cursor to the top/bottom left corner of the screen
 * /, ?:          activate input mode and search up/down
 * n, N:          repeat last search, up/down
 * s:             toggle move/selection mode
 * t:             toggle regular/rectangular selection type
 * Return:        quit keyboard_select, keeping the highlight of the selection
 * Escape:        quit keyboard_select

With h,j,k,l (also with arrow keys), you can use a quantifier. Enter a number before hitting the appropriate key.

Shortcuts for input mode :

 * Return:       Return to the previous mode

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
