# WSL2_proxy
This shell script allows the wsl instance to access proxy in windows, enabling installations of otherwise unaccessable packages such as micromamba.
## Credit
This small project is based on [this blog](https://zinglix.xyz/2020/04/18/wsl2-proxy/), but has been modified by me to make it functional on my instance.
## Before using
- open the .sh file either through windows notebook or a linux editor, go to this line:
```bash
port=7890
```
and change the port to the port of your windows proxy app (e.g. clash for windows uses  port 7890)

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

