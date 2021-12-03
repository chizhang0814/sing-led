# sing-led

1) Install the driver of led stripe,
```bash
sudo nano /boot/config.txt
#添加/修改下面两行
hdmi_force_hotplug=1
hdmi_force_edid_audio=1 
```

Configure the port in file
```bash
rpi_ws281x/python/examples/strandtest.py 
```
2) Test the led driver by, remember user `-c` otherwise the led will keep on even you quit the test
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
sudo apt install python3-pyaudio
```
5) Copy `neopixel.py` from `rpi_ws281x/python/` to `audio-reactive-led-strip/python/`
```bash
cp rpi_ws281x/python/neopixel.py audio-reactive-led-strip/python
```
modify config file
```bash
sudo nano audio-reactive-led-strip/python/config.py
1 设备改成树莓派
2 LED灯珠数量
3 期待帧率FPS改72
4 3.3v转5V的逻辑电平转换器如果没有使用改False
5 关掉可视化
```
6) connect the use microphone to your raspberry pi.

7) You can test the sing led, before you run it, remember configure it with right pin number:
```bash
sudo python3 audio-reactive-led-strip/python/visualization.py
```

8) error may occur while import pyaudio
```python
>>> import pyaudio
Could not import the PyAudio C module '_portaudio'.
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/usr/local/lib/python3.7/dist-packages/pyaudio.py", line 116, in <module>
    import _portaudio as pa
ImportError: libportaudio.so.2: cannot open shared object file: No such file or directory
```
to solve this, need to remove the existing pyaudio package, then manually complie the newest version
```bash
sudo pip3 uninstall pyaudio
wget http://files.portaudio.com/archives/pa_stable_v190700_20210406.tgz
tar -xvzf pa_stable_v190700_20210406.tgz
./configure
make
make install
```
