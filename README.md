# FbTerm - a fast FrameBuffer based TERMinal emulator for linux

## DESCRIPTION

FbTerm is a fast terminal emulator for linux with frame buffer device or VESA video card. Features include:

  * mostly as fast as terminal of linux kernel while accelerated scrolling is enabled
  * select font with fontconfig and draw text with freetype2, same as Qt/Gtk+ based GUI apps
  * dynamicly create/destroy up to 10 windows initially running default shell
  * record scrollback history for every window
  * auto-detect current locale and convert text encoding, support double width scripts like Chinese, Japanese etc
  * switch between configurable additional text encodings with hot keys on the fly
  * copy/past selected text between windows with mouse when gpm server is running
  * change the orientation of screen display, a.k.a. screen rotation
  * lightweight input method framework with client-server architecture
  * background image for eye candy

read man page doc/fbterm.1 for usage help.

### INPUT METHOD
Instead of adding input method directly in FbTerm, a client-server based input method framework is designed to do this work. FbTerm acts as a client, standalone IM program as a server, and they run in seperated processes.

If you want to develope a new IM program for FbTerm, there is a IM example in im/ directory, which help you to understand IM architecture and provide some base sources to simplify the development.

=======***********=======

sudo apk add libgc++ make g++ linux-headers gpm-dev libvterm-dev fontconfig-dev

./configure

make

vi src/mouse.cpp

add "#include <cstring>" into mouse.cpp

sudo make install

Making install in src

make[1]: Entering directory '/home/user/fbterm/src'

Making install in lib

make[2]: Entering directory '/home/user/fbterm/src/lib'

make[3]: Entering directory '/home/user/fbterm/src/lib'

make[3]: Nothing to be done for 'install-exec-am'.

make[3]: Nothing to be done for 'install-data-am'.

make[3]: Leaving directory '/home/user/fbterm/src/lib'

make[2]: Leaving directory '/home/user/fbterm/src/lib'

make[2]: Entering directory '/home/user/fbterm/src'

make[3]: Entering directory '/home/user/fbterm/src'

test -z "/usr/local/bin" || .././install-sh -c -d "/usr/local/bin"

  /usr/bin/install -c fbterm '/usr/local/bin'

make[3]: Nothing to be done for 'install-data-am'.

make[3]: Leaving directory '/home/user/fbterm/src'

make[2]: Leaving directory '/home/user/fbterm/src'

make[1]: Leaving directory '/home/user/fbterm/src'

Making install in im

make[1]: Entering directory '/home/user/fbterm/im'

make[2]: Entering directory '/home/user/fbterm/im'

make[2]: Nothing to be done for 'install-exec-am'.

make[2]: Nothing to be done for 'install-data-am'.

make[2]: Leaving directory '/home/user/fbterm/im'

make[1]: Leaving directory '/home/user/fbterm/im'

Making install in terminfo

make[1]: Entering directory '/home/user/fbterm/terminfo'

make[2]: Entering directory '/home/user/fbterm/terminfo'

make[2]: Nothing to be done for 'install-exec-am'.

tic fbterm

make[2]: tic: No such file or directory

make[2]: *** [Makefile:326: install-data-local] Error 127

make[2]: Leaving directory '/home/user/fbterm/terminfo'

make[1]: *** [Makefile:226: install-am] Error 2

make[1]: Leaving directory '/home/user/fbterm/terminfo'

make: *** [Makefile:264: install-recursive] Error 1

cat .fbtermrc 

vi .fbtermrc 

chmod u+s /usr/local/bin/fbterm
