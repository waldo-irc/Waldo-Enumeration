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
