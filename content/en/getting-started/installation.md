---
title: Installation
author: Steve_Mutter
lang: en
weight: 1
aliases:
  - /install
---
{{< tabs "Install Tab" >}}
{{< tab "Windows" >}}

# Windows

Please visit the Autodarts.com website to download Autodarts Desktop

[Autodarts.com](https://autodarts.com/downloads/)

{{< /tab >}}
{{< tab "Linux" >}}

# Linux

Please visit the Autodarts.com website to download Autodarts Desktop

[Autodarts.com](https://autodarts.com/downloads/)

## Headless (advanced)

{{<hint type=important icon=gdoc_error_outline >}}
Only for a machine without a screen — a Raspberry Pi or a mini PC you reach over SSH. Everyone else should use Autodarts Desktop above.
{{< /hint >}}

You need `curl`. Most systems have it; if yours does not:

```bash
sudo apt install curl -y
```

Then install for your user (no `sudo` needed):

```bash
curl -fsSL https://autodarts.sh | bash -s -- --headless
```

Add `--beta` to follow the beta track instead. Headless builds exist for x86_64, arm64 and 32-bit Raspberry Pi (armv7l).

Once installed, run `autodarts`. It opens the board's own screen in the terminal, where you sign in (scan the QR code or open the address it shows, on any device), create or claim your board, and set up and calibrate the cameras. Its **Service** section installs the service that keeps the board running in the background and starts it on boot.

Other commands:

```bash
autodarts remote    # manage a board elsewhere on your network, from any machine
autodarts update    # install the latest release
autodarts --help    # everything else
```

Board Manager stays available in a browser at `http://<the board's address>:3180`.

{{<hint type=warning icon=gdoc_info_outline >}}
If this machine ran the previous version (Autodarts 0.x), remove it *before* installing the new one, so the two do not fight over the cameras. Your settings in `~/.config/autodarts` are kept, and the new version picks up the board's sign-in from them.
{{< /hint >}}

```bash
sudo systemctl disable --now autodarts
sudo rm -f /etc/systemd/system/autodarts.service /etc/systemd/system/autodartsupdater.service
sudo systemctl daemon-reload
rm -rf ~/.local/opt/autodarts ~/.local/bin/autodarts ~/.local/bin/updater.sh
```

To uninstall: `curl -fsSL https://autodarts.sh | bash -s -- --uninstall --headless` (use `--purge` instead to also delete settings and calibration).

# UVC Hack

In some cases you need the UVC Hack in combination with Linux based Distros

The UVC hack eliminates issues with incorrectly requested bandwidth from multiple cameras on the same USB bus. Most cameras always request bandwidth for maximum resolution and FPS. It is sometimes needed to resolve bandwidth issues on the USB bus.

The notorious UVC hack has now become a little bit simpler. You can now install it in a similar fashion as the Autodarts board client. Make sure that curl is installed (`sudo apt install curl`). I have tested this on a variety of devices, but you can never know.

The command tries to install all necessary dependencies and then compiles the UVC driver on your device. It will try to unload the old driver and load the new one, as well as copy the new driver into the kernel so that it is loaded on restart. I have found that it is generally a good idea to have a least one camera connected when doing this. So, try to make sure that you have at least one camera connected.

Let me know how this works for you. Here is the command.

```bash
bash <(curl -sL get.autodarts.com/uvc)
```

Now the UVC Hack should work properly and you are ready to go.

You can also uninstall the UVC Hack with this command.

```bash
bash <(curl -sL get.autodarts.com/uvc) --uninstall
```

{{<hint type=warning icon=gdoc_info_outline >}}
The UVC Hack will not work on linux machines that have [UEFI Secure Boot](https://wiki.ubuntu.com/UEFI/SecureBoot) enabled.
{{< /hint >}}
{{< /tab >}}

{{< tab "macOS" >}}

# macOS

Please visit the Autodarts.com website to download Autodarts Desktop

[Autodarts.com](https://autodarts.com/downloads/)

## Headless (advanced)

To run a Mac as a board without the Desktop app, install the headless version from a terminal — no OpenCV or Homebrew needed:

```bash
curl -fsSL https://autodarts.sh | bash -s -- --headless
```

Then run `autodarts` and follow the steps on its screen, as described in the Linux tab.

{{< /tab >}}
{{< /tabs >}}
