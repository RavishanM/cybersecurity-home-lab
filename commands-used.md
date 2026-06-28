# Commands Used

## Find Kali IP Address

```bash
ip a
```

This command was used to find the Kali VM’s IP address on the home network.

## Test Connection to Mac

```bash
ping 192.168.1.x
```

This command tested if Kali could reach the Mac on the same network. The result showed replies from the Mac and 0% packet loss.

## Scan Mac for Open Ports

```bash
nmap --open 192.168.1.x
```

This command scanned the Mac and showed open ports. The scan showed Apple-related services running when AirPlay Receiver was enabled.

## Check Mac Listening Services

```bash
lsof -iTCP -sTCP:LISTEN -P -n
```

This command was run on the Mac to see which services were listening locally. It showed services listening on ports such as 5000, 50600, and 7000.

## Scan Windows PC Port 445

```bash
nmap -p 445 192.168.1.x
```

This command checked port 445 on the Windows PC. Nmap showed the port as filtered, meaning the Windows firewall was blocking or filtering the connection.
