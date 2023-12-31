---
title: Installation
author: Steve_Mutter
lang: en
weight: 1
aliases:
  - /install
---

{{< tabs "Install Tab" >}}
{{< tab "Linux" >}}

Autodarts is designed to work on every Ubuntu/Debian-based system. While it is primarily tested on Ubuntu 20.04 and 22.04, we recommend using one of these versions for optimal performance. Additionally, some community members have reported positive experiences with 'Q4OS.' If your system encounters compatibility issues with newer Ubuntu versions, you may consider testing Autodarts on 'Q4OS' as an alternative.

# Linux

## Requirements

You will also need `curl`.
You can install it like this.

```bash
sudo apt install curl -y
```

On linux distributions with different package managers, use the one provided.

## Installation

If you want to install autodarts with automatic start on boot go along with this:

```bash
bash <(curl -sL get.autodarts.io)
```

If you do not want the autostart systemd service to be installed, you can use the `-n` flag as follows.

```bash
bash <(curl -sL get.autodarts.io) -n
```

If you want to install a specific version, e.g., `0.20.0`, then you can append the required version to the command as follows.
This can be helpful if you want to downgrade to an earlier version.
This also works with the `-n` flag from before.

```bash
bash <(curl -sL get.autodarts.io) 0.20.0
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

## Requirements

The macOS version is dynamically linked and does not come with OpenCV included.
make sure that you install OpenCV 4.8.0 opencv first.

```bash
brew install opencv
```

You will also need `curl`.
You can install it like this.

```bash
brew install curl
```

## Installation

You can then install autodarts with the following command.

```bash
bash <(curl -sL get.autodarts.io)
```

If you want to install a specific version, e.g., `0.20.0`, then you can append the required version to the command as follows.
This can be helpful if you want to downgrade to an earlier version.

```bash
bash <(curl -sL get.autodarts.io) 0.20.0
```

{{< /tab >}}
{{< /tabs >}}
