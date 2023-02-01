# Collection of Python 3.9 wheels for armv7l:

This repository contains any precompiled wheels that my Banana Pi R2 router has compiled in a separate compilation environment.  These wheels are used for projects:
- [MITMProxy v9.0.1](https://mitmproxy.org/)
- [Tuya-Convert](https://github.com/ct-Open-Source/tuya-convert)

# Installation Directions:

### Install necessary Python packages:
```bash
apt update
apt install -y --no-install-recommends python3-pip python3-venv
```

Get the precompiled wheels for mitmproxy:
```bash
git clone https://github.com/xptsp/python3.9-wheels /tmp/wheels
```

### Installing MITMProxy 9.0.1:
<details>

Create mitmproxy user:
```bash
useradd -m -G users -b /opt -s /usr/sbin/nologin mitmproxy
```

Change user to "mitmproxy":
```bash
sudo -u mitmproxy -s
```

Create and activate virtual environment:
```bash
python3 -m venv /opt/mitmproxy/venv
source /opt/mitmproxy/venv/bin/activate
```

Install the precompiled wheels:
```bash
python3 -m pip install --no-index --find-links=/tmp/wheels mitmproxy
```
</details>

### Installing Tuya-Convert:
<details>

Install other packages:
```bash
apt install -y git iw dnsmasq rfkill hostapd screen curl mosquitto haveged net-tools libssl-dev python3-dev
```

Install the precompiled wheels:
```bash
python3 -m pip install --no-index --find-links=/tmp/wheels --upgrade paho-mqtt tornado sslpsk pycryptodomex
```
</details>
