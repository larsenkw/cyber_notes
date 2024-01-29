Provides a summary of the main tools used for pentesting with links to more detailed notes.

General format:
- Brief description of tool.
- Frequently used options.
- Example

# Web Applications
## [curl](curl)
Used to grab raw data from websites and other URL-based services.
## [jsconsole](https://www.jsconsole.com)
This can be used to run JavaScript code.
# Networks
## [nmap](nmap)
Scans the network for open IP addresses and ports, providing information on what applications are running on them.

Common Options:
- -p \<port ranges\>: scan a set of ports rather than all of them. Separate ports by commas, range using a dash “-”, specify UDP/TCP using “U:” or “T:” before listing the ports.
- --top-ports \<number\>: scan the top “number” most common ports.
- -A: for OS and version detection.
Example:
	$ nmap -A –top-ports 10 192.168.0.1
# Protocol-Specific
## [FTP](ftp)

## [SMB](SMB)
Server Message Block (SMB)

Discover SMB Shares:
```
$ nmap --script smb-os-discovery.nse -p<port> <host>
```
Use on a port that is running an SMB server. This can be obtained using NMAP.

Grab the OS information using:
```
$ nmap -A -p<port> <host>
```
This will help you to identify if the system may be vulnerable to certain exploits like EternalBlue.
### smbclient
"smbclient" command allows you to enumerate and interact with SMB shares.
#### Options
- -L: retrieve a list of available shares on the host
- -N: suppress the password prompt
#### Example
```
$ smbclient -N -L \\\\10.129.42.253

# Reveal users
$ smbclient \\\\10.129.42.253\\users

# Access using a specific user
smbclient -U bob \\\\10.129.42.253\\users

# You will then see
Enter WORKGROUP\bob's password: <enter password here>
Try "help" to get a list of possible commands.

smb: \> ls
```

You can use 'cd' to access a users folder. Then use 'get' to download files.