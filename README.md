# SDL2_mixer for PSP

Prerequisites:

- SDL2
- libogg (optional)
- libvorbis (optional)
- libTremor (optional)

Note: If libTremor is detected it will be used instead of libogg and libvorbis.
To disable this behavior pass --disable-music-ogg-tremor to configure.

Build procedure:

```shell
./autogen.sh
LDFLAGS="-L$(psp-config --pspsdk-path)/lib" LIBS="-lc -lpspuser" \
  ./configure --host psp --with-sdl-prefix=$(psp-config --psp-prefix) \
  --disable-music-mp3 --prefix=$(psp-config --psp-prefix) \
  --disable-music-libmikmod --enable-music-mod
make
make install
```
