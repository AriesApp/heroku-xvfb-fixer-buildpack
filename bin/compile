# symlink libs to where Xvfb searches
ln -s /lib/x86_64-linux-gnu/libudev.so.1 $1/.apt/usr/lib/libudev.so.0
ln -s /app/.apt/usr/lib/x86_64-linux-gnu/libXfont.so.1 $1/.apt/usr/lib/libXfont.so.1

# patch Xvfb to use /app/.. paths instead of hardcoded wrong values
sed -i.bak s/usr\\/bin/app\\/ubi/g $1/.apt/usr/bin/Xvfb
sed -i.bak s/usr\\/share\\/fonts/app\\/usr-s-fonts/g $1/.apt/usr/bin/Xvfb
# create symlinks for Xvfb to use /app/.apt/usr/...
ln -s /app/.apt/usr/bin $1/ubi
ln -s /app/.apt/usr/share/fonts $1/usr-s-fonts

# run mkfontdir with binaries from inside dyno
export PATH="$PATH:$1/.apt/usr/bin"
export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:$1/.apt/usr/lib:$1/.apt/usr/lib/x86_64-linux-gnu"
find $1/.apt/usr/share/fonts/X11 -type d | xargs $1/.apt/usr/bin/mkfontdir