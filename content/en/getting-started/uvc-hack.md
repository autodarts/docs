---
title: UVC Hack
author: TmO
lang: en
weight: 10
---

The notorious UVC hack has now become a little bit simpler. You can now install it in a similar fashion as the Autodarts board client. Make sure that curl is installed (`sudo apt install curl`). I have tested this on a variety of devices, but you can never know.

The command tries to install all necessary dependencies and then compiles the UVC driver on your device. It will try to unload the old driver and load the new one, as well as copy the new driver into the kernel so that it is loaded on restart. I have found that it is generally a good idea to have a least one camera connected when doing this. So, try to make sure that you have at least one camera connected.

Let me know how this works for you. Here is the command.

```bash
bash <(curl -sL get.autodarts.io/uvc)
```

Now the UVC Hack should work properly and you are ready to go.
