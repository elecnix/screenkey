screenkey
=========

Fork of http://launchpad.net/screenkey

What's up with nilcons?
=======================
We have "forked" the fork :)

Not really, this repository is just some small changes to make
screenkey more viable as a teaching tool while keeping remote courses
over VNC.  This use case is a bit different than recording a
screencast, so we have adjusted the defaults a little bit and "fixed"
one exception that made screenkey impossible to start on a modern
Ubuntu.

What's up?
==========

I've made significant changes, including:

* new command line flags:
  * `-fg` to set font color;
  * `-bg` to set background color;
  * `--no-sudo` do not perform check on launched sudo (it's currently VERY slow,
    because of this check will launch subprocess on EVERY key typed);
  * `-n, --no-hide` do not hide window after timeout, hide only text (make it
    usable with tile managers, for example, with i3, which can not have
    unfocusable windows);
* instead of removing text on `backspace` symbol `⇐` will be added; it was
  broken anyway, so it will happily erase `Ctrl+...` and other text;
* space is changed to visible character: `␣`;
* supported second keyboard layout, so not only ASCII letters can be recorded;
* way of detecting modifiers was changed and now based on pure event state
  field; it's more robust and precise, so, for example, if you remap arrow
  keys into Mod+\[HJKL\] (as I do) you get correct output (arrows, not Mod+arrows
  or something);
* `Shift+` is now not printed for characters that have two distinct states
  with and without Shift; it means, that when you type `Shift+q` you will see
  `Q`. However, if you type `Shift+Left`, you will see `Shift+←`;
* added another position modifier, and now window can be dragged around to
  choose optimal position and size; it will remembered and will not change
  after window hide/show cycle;
* font size is now binded to window height, so if you resize window you will
  get different font size;
* spacing between several keys are tweaked, so they will not nestle to each
  other, like this: `Ctrl+vhello`; instead, you will see: `Ctrl+v hello`.

Preview
=======
Some awkward highlights of this features shown here:

![output](https://cloud.githubusercontent.com/assets/674812/3472704/d75e249e-02ce-11e4-90f0-d65b575b1574.gif)

Original author
===============
Pablo Seminario

Thanks to
=========
Jacob Gardner
farrer
Ivan Makfinsky
Muneeb Shaikh

License
=======
Copyright (c) 2010 Pablo Seminario 
This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
