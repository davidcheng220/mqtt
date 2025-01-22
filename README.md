sudo apt-get install -y mosquitto mosquitto-clients
hostname -I

sudo vi /etc/mosquitto/mosquitto.conf
allow_anonymous true
listener 1883 hostip(0.0.0.0)

restart:
sudo service mosquitto stop
sudo service mosquitto start

rpi:
mosquitto_sub -h Rpi-IP -t msg/info

pip install paho-mqtt==1.6.1

see ref:
https://learningsky.io/install-mosquitto-mqtt-message-broker-on-raspberry-pi-and-python-publish-subscription/

to run after reboot
sudo systemctl daemon-reload
sudo systemctl enable mosquitto
