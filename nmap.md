# NMAP

## Basics:

#### Scan verbose

`nmap -v 10.0.0.1`

#### Scan with more verbose

`nmap -vv 10.0.0.1`

#### Scan multiple IPs

`nmap -vv 10.0.0.1 10.0.0.2 10.0.0.3`

`nmap -vv 10.0.0.1,2,3`

#### Scan a range of IPs

`nmap -vv 10.0.0.1-10`

#### Scan from a file

`nmap -iL targets.txt`
> Targets in the input file must be separed by space, tab or newline.

> Target can be an IP, Subnet, Range, IPv4, IPv6 or octet range

> Use --exclude to exclude targets

> Use --excludefile to exclude targets based on a file

#### Ping scan a subnet:

`nmap 10.0.0.0/24`
> for subnets, use ping scan 

`nmap -sn 10.0.0.0/24` 

#### Find listening protocols

`nmap -sO 10.0.0.1`

#### TCP scan:

`nmap -sT 10.0.0.1`

#### UDP scan:

`nmap -sU 10.0.0.1`

#### TCP SYN scan:

`nmap -sS 10.0.0.1`

#### Scan specific ports

`nmap -p 80 10.0.0.1`

#### Scan multiple ports

`nmap -p 80,443 10.0.0.1`

#### Scan multiple ports using different protocols

`nmap -p T:80,U:514 10.0.0.1`

#### T4 timing Full TCP port scan + Standard service version detection:

`nmap -p- -sV -sS -T4 10.0.0.1`

#### T4 timing Stealth SYN scan + OS and services version detection + verbose

`nmap -v -A -sS -T4 10.0.0.1`

#### T4 timing Stealth SYN scan + OS and services version detection + more aggressive service detection + verbose

`nmap -v -A --version-intensity 5 -sS -T4 10.0.0.1`

#### T4 timing Full port Stealth SYN scan + OS and services version detection + light service banner detection + verbose

`nmap -v -p- -A --version-intensity 0 -sS -T4 10.0.0.1`

## Scripts

#### Locate scripts

`locate nse | grep script`

#### Standard script scan

`nmap -sV -sC 10.0.0.1`

#### Script scan

`nmap -sV -p 80 --script=http* 10.0.0.1`

#### Standard HTTP/HTTPS port 80, 443 scan + Nikto vulnerability scanning

`nmap -p80,443 10.0.0.1 -oG - | nikto.pl -h -`

