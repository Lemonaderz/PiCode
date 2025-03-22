**How to upload code to Pico for Pulse+Vent:**
Install Thonny: https://thonny.org
Connect pico while holding bootsel
Install micropython on pico
Save PicoCode file as main.py
restart


**How to setup Zero for Laryng App:**
pip install motion
To fix error: go to line 312 in the error file, delete the broken line, delete the following lines with just a period. 
Motion Settings to change in config:
add: stream_maxrate 100
add: stream_quality 100
width 150
height 150
text_left ""
text_right ""
movie_output off
picture_output off
emulate_motion on 
stream_localhost off

crontab -e
Write:
@reboot sleep 15 && sudo motion > /home/cronlog 2>&1
at the bottom
run:
sudo nmcli con delete SIM3D
sudo nmcli con add type wifi ifname wlan0 mode ap con-name SIM3D ssid SIM3D autoconnect true
sudo nmcli con modify SIM3D 802-11-wireless.band bg
sudo nmcli con modify SIM3D 802-11-wireless.channel 3
sudo nmcli con modify SIM3D 802-11-wireless.cloned-mac-address 00:12:34:56:78:9a
sudo nmcli con modify SIM3D ipv4.method shared ipv4.address 192.168.0.1/24
sudo nmcli con modify SIM3D ipv6.method disabled
sudo nmcli con modify SIM3D wifi-sec.key-mgmt wpa-psk
sudo nmcli con modify SIM3D wifi-sec.psk "sim3d123"
sudo nmcli con up SIM3D


