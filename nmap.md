# nmap
## Description
### Brief
Scans the network for open IP addresses and ports, providing information on what applications are running on them.

### Detail
nmap scans a network over a defined range of IP addresses and ports and performs actions based on the options provided. It is a useful tool to explore a network and attempt to discover the types of devices and services that are available and/or running. When running the command, it will perform a scan over the 1000 most common ports by default.

There are scripts that nmap can run during the scan. By using the -sC command, nmap will run scripts that are useful to try and obtain more information about the devices and services. Use the --script option to specify the name of a script to run. Use the "locate" tool to search for where the scripts are to see what scripts are available for nmap. This is accomplished by:
```
$ locate nmap/scrips
```

## Options
- -p \<port ranges\>: scan a set of ports rather than all of them. Separate ports by commas, range using a dash “-”, specify UDP/TCP using “U:” or “T:” before listing the ports.
- --top-ports \<number\>: scan the top “number” most common ports.
- -A: for OS and version detection.
- -sC: run common scripts to obtain more information
- -sV: run version scan and identify the service protocol, application name, and version
## Scripts
Gather banner information.
```
$ nmap -sV --script=banner <target>
```
## Examples
