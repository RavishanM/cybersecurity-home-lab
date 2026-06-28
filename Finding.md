# Lab Findings

## Kali IP Address

I used `ip a` in Kali Linux to find the VM’s IP address. This confirmed that Kali was connected to my home network through Bridged Adapter mode.

## Ping Test

I used `ping` from Kali to test if my Mac was reachable on the same network.

The ping test worked and showed 0% packet loss. This means Kali and my Mac were able to communicate with each other.

## Mac Nmap Scan

I used `nmap --open` to scan my Mac for open ports.

The scan showed open ports such as:

```text
5000/tcp open
7000/tcp open
```

These ports appeared to be related to Apple services such as AirPlay or nearby device communication.

## AirPlay Receiver Test

I turned off AirPlay Receiver on my Mac and ran the Nmap scan again.

After turning it off, the open ports disappeared. This showed me that device settings can affect which ports are visible on the network.

## Mac Local Services

I used this command on my Mac:

```bash
lsof -iTCP -sTCP:LISTEN -P -n
```

This showed which services were listening locally on the Mac.

This helped me compare:

* What the Mac was running internally
* What Kali could see from outside using Nmap

## Windows PC Port 445 Scan

I scanned port 445 on my Windows PC using:

```bash
nmap -p 445 192.168.1.x
```

The result showed port 445 as filtered.

This means the Windows firewall was blocking or filtering the connection, which is good for security.

## What I Learned

From this lab, I learned about:

* IP addresses
* Ping
* Nmap scanning
* Open ports
* Filtered ports
* Firewalls
* How computer settings affect network visibility

## Safety Note

This lab was done only on my own devices and my own home network.
