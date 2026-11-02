## rNano 9.3

Old terminal-based editor based on GNU Nano.

I only use this because I am used to it. I have been using this editor for
years.

This code is barely maintained, the only time I *ever* commit on this repo
is for code merges, for newer verisons of GNU Nano, that's it.


Install deps:
```
sudo dnf install git gcc make autoconf automake gettext gettext-devel groff texinfo pkgconf-pkg-config ncurses-devel
```
Build:
```
make clean
./autogen.sh
./configure --prefix="/usr"
make -j$(nproc)
```
Install:
```
sudo dnf remove nano
sudo rm -rfv /usr/bin/nano /usr/bin/rnano
sudo make install
rm -rfv ~/.nanorc
printf 'include "/usr/share/nano/*.nanorc"\ninclude "/usr/share/nano/extra/*.nanorc"\n' >> ~/.nanorc
```
Full:
```
make clean
./autogen.sh
./configure --prefix="/usr"
make -j$(nproc)
sudo dnf remove nano
sudo rm -rfv /usr/bin/nano /usr/bin/rnano
sudo make install
rm -rfv ~/.nanorc
printf 'include "/usr/share/nano/*.nanorc"\ninclude "/usr/share/nano/extra/*.nanorc"\n' >> ~/.nanorc
```

This should work on Fedora.
