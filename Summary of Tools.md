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