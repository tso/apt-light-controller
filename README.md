# apt-light-controller

trivial web ui for controlling my apt lights

Systemd Config:

```
[Unit]
Description=Flask app controlling apt lights
After=multi-user.target
Requires=network.target

[Service]
WorkingDirectory=~/Development/apt-light-controller
Type=idle
ExecStart=flask run --host=0.0.0.0 --port=80

[Install]
WantedBy=multi-user.target
```

Setup:

```
$ sudo nano /etc/systemd/system/light-controller.service
$ sudo chmod 644 /etc/systemd/system/light-controller.service
$ sudo systemctl daemon-reload
$ sudo systemctl enable light-controller.service
```
