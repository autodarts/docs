---
title: FAQ
author: Steve_Mutter
lang: en
weight: 60
aliases:
  - /faq
draft: true
---

{{< tabs "Install Tab" >}}
{{< tab "Linux" >}}

# Linux

{{< expand "Error: bash: /dev/fd/63: No such file or directory." "..." >}}

## Solution 1:
If you encounter an error while attempting to install Autodarts using the one-line command:
```bash
bash <(curl -sL get.autodarts.io) -n
```

please try installing Autodarts without the "-n" flag by using the following command: 
```bash
bash <(curl -sL get.autodarts.io)
```
 After successful installation, enable autostart with the following command: 
```bash
sudo systemctl enable autodarts
```

## Solution 2:
Alternatively, you can use "wget" to install Autodarts:
```bash
wget -c https://get.autodarts.io/ -O install.sh
```
Followed by:
```bash
bash install.sh
```

{{<hint type=info icon=gdoc_info_outline >}}
In both cases, "curl" has to be installed:
```bash
sudo apt install curl -y
```
{{< /hint >}}

{{< /expand >}}


{{< /tab >}}
{{< tab "Windows" >}}

# Windows

{{< /tab >}}
{{< tab "macOS" >}}

# macOS

{{< /tab >}}
{{< /tabs >}}
