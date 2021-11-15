---
title: How to Connect to an OpenVPN server
description: Detecting and using keypress events is dead easy in Svelte. Make your app feel native with a few lines of code.
slug: openvpn
author: Mark Lumbao
authorImage: https://avatars.githubusercontent.com/u/814405?v=4
date: 11/15/21
---

## Steps

- Install open vpn
​
  This will depend on the distro you're using.
​
  **Example**:
​
  _In Arch_
​
  ```
  sudo pacman -S openvpn
  ```
​
  _In Ubuntu_
​
  ```
  sudo apt-get install openvpn
  ```
​
- Open the URL of the openvpn server you're trying to connect to.
  This should be given you by your systems administrator. It usually
  comes in this format `https://{the-ip-address-of-the-server}/?src=connect`.
  Login with the given credentials.
​
- After logging in there should be a label there saying:
  **Available Connection Profiles:** just click the item labeled _Yourself (user-locked profile)_.
  That should prompt you to save a file named **client.ovpn**. Save it somewhere safe.
​
- After downloading the **client.ovpn** file cd into its location then run this command:
​
  ```
  sudo openvpn --config client.ovpn
  ```
​
- If everything goes as expected you should see a message ending in `Initialization Sequence Completed`.
​
### Congratulations you have now connected to you OpenVPN server!
