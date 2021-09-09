# sing-led





If you see error like this:
```bash
libf77blas.so.3: cannot open shared file: no such file or directory 
```
Just need to run
```bash
sudo apt-get install libatlas-base-dev
```


Install python dependencies using sudo
```bash
sudo pip3 install numpy
sudo pip3 install scipy
sudo pip3 install pyaudio
```

copy `neopixel.py` from `rpi_ws281x/python/` to `audio-reactive-led-strip/python/`
```bash
cp rpi_ws281x/python/neopixel.py audio-reactive-led-strip/python
```
