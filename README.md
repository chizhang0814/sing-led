# sing-led

1) Install the driver of led stripe, configure the port in file
```bash
rpi_ws281x/python/examples/strandtest.py 
```
2) Test the led driver by 
```bash
sudo python rpi_ws281x/python/examples/strandtest.py  -c
```
3) After you install the driver when you run the test if you see error like this:
```bash
libf77blas.so.3: cannot open shared file: no such file or directory 
```
Just need to run
```bash
sudo apt-get install libatlas-base-dev
```

4) If dependencies are missing install python dependencies using sudo
```bash
sudo pip3 install numpy
sudo pip3 install scipy
sudo pip3 install pyaudio
```
5) Copy `neopixel.py` from `rpi_ws281x/python/` to `audio-reactive-led-strip/python/`
```bash
cp rpi_ws281x/python/neopixel.py audio-reactive-led-strip/python
```
6) connect the use microphone to your raspberry pi.

7) You can test the sing ledl, before you run it, remember configure it with right pin number:
```bash
sudo python3 audio-reactive-led-strip/python/visualization.py
```
