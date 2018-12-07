# pilight2mqtt
Proxy messages between pilight and mqtt


# Installation
python3 setup.py install


# Tips & Tricks
- Autodiscovery fails, what is the port to use?

You can specify the port pilight listens on in the pilight configuration 
under settings, port. https://manual.pilight.org/en/configuration-settings#pf2

Remember to first stop pilgith and only modify the settings afterwards. At least
for me pilight will overwrite the configuration with its current values when shutting
down.



# Requirements
* Python 3.4+


# systemd service
Modify pilight2mqtt.service with the start argumetns you need

```
cp pilight2mqtt.service /lib/systemd/system/pilight2mqtt.service
systemctl daemon-reload
systemctl start pilight2mqtt.service
systemctl enable pilight2mqtt.service
```