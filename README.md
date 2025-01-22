sudo apt-get install -y mosquitto mosquitto-clients<br>
hostname -I<br>

sudo vi /etc/mosquitto/mosquitto.conf<br>
allow_anonymous true <br>
listener 1883 hostip(0.0.0.0)<br>

restart:
sudo service mosquitto stop<br>
sudo service mosquitto start<br>

rpi:
mosquitto_sub -h Rpi-IP -t msg/info<br>

pip install paho-mqtt==1.6.1<br>

see ref:
https://learningsky.io/install-mosquitto-mqtt-message-broker-on-raspberry-pi-and-python-publish-subscription/<br>

to run after reboot
sudo systemctl daemon-reload<br>
sudo systemctl enable mosquitto<br>
