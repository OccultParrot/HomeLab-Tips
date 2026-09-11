# Setting Up Tailscale

Tailscale is what I am using the create a VPN across all my devices in order to connect to them all. It is fairly simple to set up.

## Windows
Install the .exe from [here](https://tailscale.com/download), and run it. After it installs it will prompt you to log in, after that you are connected!

## Linux
In this example I will be using Arch because that is the distro I personally use. You can install it with the `pacman` package manager easily.
```bash
sudo pacman -S tailscale
```
Once its installed, start the client with
```bash
tailscale up
```
This should prompt you to enter a link to register the device with tailscale.

All together the installation is just two commands:
```bash
sudo pacman -S tailscale
tailscale up
```
