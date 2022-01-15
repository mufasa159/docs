## Installing NordVPN on Debian, Ubuntu, Raspberry Pi, Elementary OS & Linux Mint
  
The **NordVPN native application** is the **recommended option** for connecting to NordVPN servers on your Linux device. We designed it with your experience in mind, giving easy access to features such as [CyberSec](https://nordvpn.com/features/cybersec/), auto-connect, and automated [Kill Switch](https://nordvpn.com/features/kill-switch-technique/).

This tutorial explains how to download and install the NordVPN app, log in, and connect to our servers. You can also find an explanation of various settings.


### Downloading the app. 

1. Download the NordVPN Linux client by opening the terminal, writing the command below, and following any on-screen instructions:  
`sh <(curl -sSf https://downloads.nordcdn.com/apps/linux/install.sh)`  
  
    **Note:** If you do not have a **curl** package, evidenced by the fact that the above does not work, you can alternatively use this command:  
`sh <(wget -qO - https://downloads.nordcdn.com/apps/linux/install.sh)`
  
    Additionally, if you receive the following issue: `Whoops! Permission denied accessing /run/nordvpn/nordvpnd.sock`, all you need to do is write the following command: `sudo usermod -aG nordvpn $USER` and then reboot your device.

2. Log in to your NordVPN account: `nordvpn login`

3. Connect to a NordVPN server: `nordvpn connect`


### Settings

To access the NordVPN client settings, type the nordvpn command in Terminal. Here is the list of available commands:   

| Command    | Description                          |
|---------------------------|-----------------------------------------------------------------------|
| `nordvpn login`           | Log in                                                                |  
|`nordvpn connect` or `nordvpn c`| Connect to VPN. To connect to specific servers, use `nordvpn connect <country_code server_number>` (eg. `nordvpn connect uk715`)  |
|`nordvpn disconnect` or `nordvpn d` | Disconnect from VPN  |
|`nordvpn connect US -g double_vpn` | Connect to a Double VPN server where the first hop is a specific country  |
|`nordvpn connect P2P` | connect to a P2P server.  |
|`nordvpn connect The_Americas` | connect to servers located in the Americas  |
|`nordvpn connect Dedicated_IP` | connect to a Dedicated IP server.  |
|`nordvpn set cybersec on` or `off` | Enable or disable CyberSec  |
|`nordvpn set killswitch on` or `off` | Enable or disable Kill Switch  |
|`nordvpn set autoconnect on` or `off` | Enable or disable auto-connect. You can set a specific server for automatic connection using nordvpn set autoconnect on country_code+server_number. Example: `nordvpn set autoconnect on us2435`  |
|`nordvpn set notify on` or `off` | Enable or disable notifications  |
|`nordvpn set dns 1.1.1.1 1.0.0.1` | Set custom DNS (you can set up a single DNS or two like shown in this command).  |
|`nordvpn set protocol udp` or `tcp` | Switch between UDP and TCP protocols  |
|`nordvpn set obfuscate on` or `off` | Enable or disable Obfuscated Servers  |
|`nordvpn set technology` | Set connection technology (OpenVPN or NordLynx)  |
|`nordvpn whitelist add port 22` | Add a rule to whitelist a specified incoming port. You can also whitelist multiple ports — just separate their numbers with a space.  |
|`nordvpn whitelist remove port 22` | Remove the rule to whitelist a specified port.  |
|`nordvpn whitelist add subnet 192.168.0.0/16` | Add a rule to whitelist a specified subnet.  |
|`nordvpn whitelist remove subnet 192.168.0.0/16`  | Remove the rule to whitelist a specified subnet.  |
|`nordvpn account` | See account information  |
|`nordvpn register` | Register a new user account | 
|`nordvpn rate` | Rate your last connection quality (1-5)   |
|`nordvpn settings` | See the current settings.  |
|`nordvpn status` | See the connection status.  |
|`nordvpn countries` | See the country list.  |
|`nordvpn cities`| See the city list. E.g.: `nordvpn cities united_states`    |
|`nordvpn groups` | See a list of available server groups.  |
|`nordvpn logout` | Log out.  |
|`nordvpn help or nordvpn h` | See the list of available commands or help for a specific command.  |
  
You can get an extensive explanation of all commands by using the `man nordvpn` command in Terminal.  


### Troubleshooting connectivity Linux

If you’re having trouble connecting to NordVPN on your Linux device using the NordVPN app, there are a few adjustments you can try. Check if the issue remains after following each set of instructions.

1. Update the NordVPN app:  
Open the terminal.  
Type the following commands to update the app:  
`sudo apt update (or sudo apt-get update)`  
`sudo apt upgrade (or sudo apt-get upgrade)`  

2. Reinstall the app:  
Type the following command to remove the app:  
`sudo apt --purge autoremove nordvpn* (or sudo apt-get --purge autoremove nordvpn*)`   
Reinstall the app.  
  
3. Use a manual connection method:  
If the issue remains, try connecting using the [manual connection method](https://support.nordvpn.com/Connectivity/Linux/1047409422/How-can-I-connect-to-NordVPN-using-Linux-Terminal.htm).  

  
Tip: Don't forget to use a strong password for your NordVPN account, as it will help you to avoid [credential stuffing](https://nordpass.com/blog/what-is-credential-stuffing/) attacks and will keep your account safe.  
   

_Source: https://support.nordvpn.com/Connectivity/Linux/1325531132/Installing-and-using-NordVPN-on-Debian-Ubuntu-Raspberry-Pi-Elementary-OS-and-Linux-Mint.htm_