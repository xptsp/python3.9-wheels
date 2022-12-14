# How To Install

Install necessary packages:
```bash
apt install -y --no-install-recommends python3-pip python3-venv
```

Create mitmproxy user:
```bash
useradd -m -G users -b /opt -s /usr/sbin/nologin mitmproxy
```

Get the precompiled wheels for mitmproxy:
```bash
git clone https://github.com/xptsp/python3.9-wheels /tmp/wheels
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
python3 -m pip install --no-index --find-links=/tmp/wheels/mitmproxy mitmproxy
```
