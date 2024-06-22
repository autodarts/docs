---
title: Installation
author: Steve_Mutter
lang: en
weight: 1
aliases:
  - /install
---

{{<hint type=note icon=gdoc_info_outline >}}
Please note that Autodarts is primarily developed for Linux-based systems. While there are setups available for Windows and macOS, they are currently in alpha release and may contain bugs.
{{< /hint >}}

{{< tabs "Install Tab" >}}
{{< tab "Linux" >}}

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

# UVC Hack


In some cases you need the UVC Hack in combination with Linux based Distros

The UVC hack eliminates issues with incorrectly requested bandwidth from multiple cameras on the same USB bus. Most cameras always request bandwidth for maximum resolution and FPS. It is sometimes needed to resolve bandwidth issues on the USB bus.

The notorious UVC hack has now become a little bit simpler. You can now install it in a similar fashion as the Autodarts board client. Make sure that curl is installed (`sudo apt install curl`). I have tested this on a variety of devices, but you can never know.

The command tries to install all necessary dependencies and then compiles the UVC driver on your device. It will try to unload the old driver and load the new one, as well as copy the new driver into the kernel so that it is loaded on restart. I have found that it is generally a good idea to have a least one camera connected when doing this. So, try to make sure that you have at least one camera connected.

Let me know how this works for you. Here is the command.

```bash
bash <(curl -sL get.autodarts.io/uvc)
```

Now the UVC Hack should work properly and you are ready to go.

You can also uninstall the UVC Hack with this command.

```bash
bash <(curl -sL get.autodarts.io/uvc) --uninstall
```

{{<hint type=warning icon=gdoc_info_outline >}}
The UVC Hack will not work on linux machines that have [UEFI Secure Boot](https://wiki.ubuntu.com/UEFI/SecureBoot) enabled.
{{< /hint >}}
{{< /tab >}}
{{< tab "Windows" >}}

# Windows

First of all you have to download the Autodarts Desktop Client from Github or from the website:

[Download Github](https://github.com/autodarts/releases/releases)

[Autodarts.io](https://autodarts.io/downloads/)

{{< /tab >}}
{{< tab "macOS" >}}

# macOS

First of all you have to download the Autodarts Desktop Client from Github or from the website:

[Download Github](https://github.com/autodarts/releases/releases)

[Autodarts.io](https://autodarts.io/downloads/)



If you want to use your Mac Headless you have to install Autodarts "the old" way:

{{<hint type=important icon=gdoc_error_outline >}}
Use this way only if you want to use your System Headless, otherwise use the Desktop Client.
{{< /hint >}}

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
