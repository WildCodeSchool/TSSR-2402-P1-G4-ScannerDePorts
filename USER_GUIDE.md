Nmap 7.91 ( https://nmap.org )
Usage: nmap [Scan Type(s)] [Options] {target specification}

TARGET SPECIFICATION:
  Can pass hostnames, IP addresses, networks, etc.
  Ex: scanme.nmap.org, microsoft.com/24, 192.168.0.1; 10.0.0-255.1-254
  nmap -iL <inputfilename>: Input from list of hosts/networks
  nmap -iR <num hosts>: Choose random targets
  nmap --exclude <host1[,host2][,host3],...>: Exclude hosts/networks
  nmap --excludefile <exclude_file>: Exclude list from file
  
HOST DISCOVERY:
  nmap -sL: List Scan - simply list targets to scan
  nmap -sn: Ping Scan - disable port scan
  nmap -Pn: Treat all hosts as online -- skip host discovery
  nmap -PS/PA/PU/PY[portlist]: TCP SYN/ACK, UDP or SCTP discovery to given ports
  nmap -PE/PP/PM: ICMP echo, timestamp, and netmask request discovery probes
  nmap -PO[protocol list]: IP Protocol Ping
  nmap -n/-R: Never do DNS resolution/Always resolve [default: sometimes]
  nmap --dns-servers <serv1[,serv2],...>: Specify custom DNS servers
  nmap --system-dns: Use OS's DNS resolver
 
SCAN TECHNIQUES:
  nmap -sS/sT/sA/sW/sM: TCP SYN/Connect()/ACK/Window/Maimon scans
  nmap -sU: UDP Scan
  nmap -sN/sF/sX: TCP Null, FIN, and Xmas scans
  nmap --scanflags <flags>: Customize TCP scan flags
  nmap -sI <zombie host[:probeport]>: Idle scan
  nmap -sY/sZ: SCTP INIT/COOKIE-ECHO scans
  nmap -sO: IP protocol scan
  nmap -b <FTP relay host>: FTP bounce scan
  
PORT SPECIFICATION AND SCAN ORDER:
  nmap -p <port ranges>: Only scan specified ports
    Ex: -p22; -p1-65535; -p U:53,111,137,T:21-25,80,139,8080,S:9
  nmap --exclude-ports <port ranges>: Exclude the specified ports from scanning
  nmap -F: Fast mode - Scan fewer ports than the default scan
  nmap -r: Scan ports consecutively - don't randomize
  nmap --top-ports <number>: Scan <number> most common ports
  nmap --port-ratio <ratio>: Scan ports more common than <ratio>
  
SERVICE/VERSION DETECTION:
  nmap -sV: Probe open ports to determine service/version info
  nmap --version-intensity <level>: Set from 0 (light) to 9 (try all probes)
  nmap --version-light: Limit to most likely probes (intensity 2)
  nmap --version-all: Try every single probe (intensity 9)
  nmap --version-trace: Show detailed version scan activity (for debugging)
  
SCRIPT SCAN:
  nmap -sC: equivalent to --script=default
  nmap --script=<Lua scripts>: <Lua scripts> is a comma separated list of directories, script-files or script-categories
  nmap --script-args=<n1=v1,[n2=v2,...]>: provide arguments to scripts
  nmap --script-args-file=filename: provide NSE script args in a file
  nmap --script-trace: Show all data sent and received by scripts
  nmap --script-updatedb: Update the script database.
  nmap --script-help=<Lua scripts>: Show help about scripts.
  nmap --script-args-help=<Lua scripts>: Show help about script arguments.
  
OS DETECTION:
  nmap -O: Enable OS detection
  nmap --osscan-limit: Limit OS detection to promising targets
  nmap --osscan-guess: Guess OS more aggressively
  
TIMING AND PERFORMANCE:
  Options which take <time> are in seconds, or append 'ms' (milliseconds),
  's' (seconds), 'm' (minutes), or 'h' (hours) to the value (e.g. 30m).
  nmap -T<0-5>: Set timing template (higher is faster)
  nmap --min-hostgroup/max-hostgroup <size>: Parallel host scan group sizes
  nmap --min-parallelism/max-parallelism <numprobes>: Probe parallelization
  nmap --min-rtt-timeout/max-rtt-timeout/initial-rtt-timeout <time>: Specifies
      probe round trip time.
  nmap --max-retries <tries>: Caps number of port scan probe retransmissions.
  nmap --host-timeout <time>: Give up on target after this long
  nmap --scan-delay/--max-scan-delay <time>: Adjust delay between probes
  nmap --min-rate <number>: Send packets no slower than <number> per second
  nmap --max-rate <number>: Send packets no faster than <number> per second
  
FIREWALL/IDS EVASION AND SPOOFING:
  nmap -f; --mtu <val>: fragment packets (optionally w/given MTU)
  nmap -D <decoy1,decoy2[,ME],...>: Cloak a scan with decoys
  nmap -S <IP_Address>: Spoof source address
  nmap -e <iface>: Use specified interface
  nmap -g/--source-port <portnum>: Use given port number
  nmap --proxies <url1,[url2],...>: Relay connections through HTTP/SOCKS4 proxies
  nmap --data <hex string>: Append a custom payload to sent packets
  nmap --data-string <string>: Append a custom ASCII string to sent packets
  nmap --data-length <num>: Append random data to sent packets
  nmap --ip-options <options>: Send packets with specified ip options
  nmap --ttl <val>: Set IP time-to-live field
  nmap --spoof-mac <mac address/prefix/vendor name>: Spoof your MAC address
  nmap --badsum: Send packets with a bogus TCP/UDP/SCTP checksum
  
OUTPUT:
  nmap -oN/-oX/-oS/-oG <file>: Output scan in normal, XML, s|<rIpt kIddi3,
     and Grepable format, respectively, to the given filename.
  nmap -oA <basename>: Output in the three major formats at once
  nmap -v: Increase verbosity level (use -vv or more for greater effect)
  nmap -d: Increase debugging level (use -dd or more for greater effect)
  nmap --reason: Display the reason a port is in a particular state
  nmap --open: Only show open (or possibly open) ports
  nmap --packet-trace: Show all packets sent and received
  nmap --iflist: Print host interfaces and routes (for debugging)
  nmap --append-output: Append to rather than clobber specified output files
  nmap --resume <filename>: Resume an aborted scan
  nmap --stylesheet <path/URL>: XSL stylesheet to transform XML output to HTML
  nmap --webxml: Reference stylesheet from Nmap.Org for more portable XML
  nmap --no-stylesheet: Prevent associating of XSL stylesheet w/XML output
  
MISC:
  nmap -6: Enable

 IPv6 scanning
  nmap -A: Enable OS detection, version detection, script scanning, and traceroute
  nmap --datadir <dirname>: Specify custom Nmap data file location
  nmap --send-eth/--send-ip: Send using raw ethernet frames or IP packets
  nmap --privileged: Assume that the user is fully privileged
  nmap --unprivileged: Assume the user lacks raw socket privileges
  nmap -V: Print version number
  nmap -h: Print this help summary page.
  
EXAMPLES:
  nmap -v -A scanme.nmap.org
  nmap -v -sn 192.168.0.0/16 10.0.0.0/8
  nmap -v -iR 10000 -Pn -p 80
SEE THE MAN PAGE (https://nmap.org/book/man.html) FOR MORE OPTIONS AND EXAMPLES



