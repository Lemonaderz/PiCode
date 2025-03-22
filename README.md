``` **How to upload code to Pico for Pulse+Vent:** <br/>
Install Thonny: https://thonny.org<br/>
Connect pico while holding bootsel<br/>
Install micropython on pico<br/>
Save PicoCode file as main.py<br/>
restart<br/>
```

``` **How to setup Zero for Laryng App:** <br/>
pip install motion <br/>
To fix error: go to line 312 in the error file, delete the broken line, delete the following lines with just a period. <br/>
Motion Settings to change in config: <br/>
add: stream_maxrate 100 <br/>
add: stream_quality 100 <br/>
width 150 <br/>
height 150 <br/>
text_left "" <br/>
text_right "" <br/>
movie_output off <br/>
picture_output off <br/>
emulate_motion on <br/>
stream_localhost off <br/>

crontab -e <br/>
Write: <br/>
@reboot sleep 15 && sudo motion > /home/cronlog 2>&1 <br/>
at the bottom <br/>
run: <br/>
sudo nmcli con delete SIM3D <br/>
sudo nmcli con add type wifi ifname wlan0 mode ap con-name SIM3D ssid SIM3D autoconnect true <br/>
sudo nmcli con modify SIM3D 802-11-wireless.band bg <br/>
sudo nmcli con modify SIM3D 802-11-wireless.channel 3 <br/>
sudo nmcli con modify SIM3D 802-11-wireless.cloned-mac-address 00:12:34:56:78:9a <br/>
sudo nmcli con modify SIM3D ipv4.method shared ipv4.address 192.168.0.1/24 <br/>
sudo nmcli con modify SIM3D ipv6.method disabled <br/>
sudo nmcli con modify SIM3D wifi-sec.key-mgmt wpa-psk <br/>
sudo nmcli con modify SIM3D wifi-sec.psk "sim3d123"  <br/>
sudo nmcli con up SIM3D  <br/>
```

