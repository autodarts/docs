---
title: Installation
author: Steve_Mutter
lang: en
weight: 1
---

{{< tabs "Install Tab" >}}
{{< tab "Linux" >}}

## Linux / Raspberry Pi

You can install Autodarts on a Linux system by using this single command.
It will automatically download the latest version and install a systemd service to automatically start Autodarts on startup.

### Requirements

You might have to install `curl` on your machine beforehand.
You can check if `curl` with this command:

```bash
curl --version
```

Output should be:

```bash
curl 7.81.0 (x86_64-pc-linux-gnu)
```

If you haven't installed curl yet you can do this by typing following command:

```bash
sudo apt install curl -y
```

### Autodarts

If you want to install autodarts with automatic start on boot go along with this:

```bash
bash <(curl -sL get.autodarts.io)
```

If you do not want the autostart systemd service to be installed, you can use the `-n` flag as follows.

```bash
bash <(curl -sL get.autodarts.io) -n
```

If you want to install a specific version, e.g., `0.16.0`, then you can append the required version to the command as follows.
This can be helpful if you want to downgrade to an earlier version.
This also works with the `-n` flag from before.

```bash
bash <(curl -sL get.autodarts.io) 0.16.0
```

You can control the the `autodarts.service` with the `systemctl` command.

```bash
sudo systemctl start autodarts
sudo systemctl stop autodarts
sudo systemctl restart autodarts
sudo systemctl status autodarts
sudo systemctl disable autodarts
sudo systemctl enable autodarts
```

If you want to see the log output, you can use the following command.

```bash
journalctl -u autodarts -f
```

{{< /tab >}}
{{< tab "Windows" >}}

# Windows

Windows is quite picky when it comes to connecting multiple cameras to the same USB port.
It is adviced to connect every camera individually to different USB ports.
It is tested on multiple machines, and this generally seems to work.
It is not guaranteed to work, though.
Windows support is still young, and things might break.
Please be patient.

{{< /tab >}}
{{< tab "macOS" >}}

# macOS

The MacOS version is dynamically linked and does not come with OpenCV included.
make sure that you install OpenCV 4.7.0 opencv first.

```bash
brew install opencv
```

{{< /tab >}}
{{< /tabs >}}
