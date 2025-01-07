# WSL2_proxy
This shell script allows the wsl instance to access proxy in windows, enabling installations of otherwise unaccessable packages such as micromamba.
## Credit
This small project is based on [this blog](https://zinglix.xyz/2020/04/18/wsl2-proxy/), but has been modified by me to make it functional on my instance.
## Important Update!
As of Jan 7th 2025, this method works on some PCs and not others. For newer Windows 11 users (> 22h2), an alternative method is to create a .wslconfig file under your C:/User/YourUserName directory, and edit it with 
```config
[wsl2]
networkingMode=mirrored
```
This would allow WSL2 to directly use your Windows proxy without additional configurations.
## Before using
- open the .sh file either through windows notebook or a linux editor, go to this line:
```bash
port=7890
```
and change the port to the port of your windows proxy app (e.g. Clash for Windows uses  port 7890)

- Make sure the allow LAN function is enabled on your windows proxy app.
## How to use
Set the proxy with this line, where /proxy.sh is where the file is located
```bash
. ./proxy.sh set
```

revert settings to default with
```bash
. ./proxy.sh unset
```

This line shows the windows gateway ip, WSL ip and current proxy settings.
```bash
. ./proxy.sh test
```

