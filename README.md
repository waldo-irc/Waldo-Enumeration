#Waldo Enumeration - Current Version 1.0.2

This script is another work in progress with updates to come.  I got frustrated of opening several terminals or tmux windows and running several scans at once and decided to automate it.  Starts with an Nmap, based on open ports it will suggest what to do next.  If SMB is detected, SMBScan is recommended for further scanning.  Also runs vuln NSE scripts for HTTP and does zonefile transfers and gathers information about a domain using "brush".

Nmap Full Vuln Scan
<br />
Usage: wenum <target> [options]
<br />
options:
<br />
-h, --help                    Show Brief Help
<br />
-l                            Search for NSE Vuln Scripts
<br />
-la                           Search through all NSE Scripts
<br />
-hv                           Run all HTTP Vuln NSE's against target
<br />
-s                            Run the Full Powerhouse Suite
<br />
-cs                           Run NSE Script against Target
<br />
-b                            Run Brush Script against Target
<br />
-stryngs                      Run the stryngs Verb Tampering Special :D
<br />
-stryngsx                     Run the Verb Tamper with PUT RCE <TARGET>
<br />
-z                            Run a zonefile transfer against a target domain
<br />
--update                      Updates wenum

#Usage Examples
wenum is a script made to quickly fully enumerate a server.  

wenum 192.168.1.1 -s

This command runs the full powerhouse.  It does a full nmap port scan with banner grabbing and the works, if ports 80 or 443 are detected it lets you further nikto and dirbuster them, if ports 139 or 445 are open it alerts you so you can use wsmb or another program to poke around SMB.  

wenum google.com -z

This runs a quick zonefile transfer against all nameservers of the target.

All output is saved to a folder with the hostname/(last 2 digits of IP)-enum.
