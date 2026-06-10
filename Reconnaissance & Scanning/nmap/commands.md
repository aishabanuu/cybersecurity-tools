# Nmap Commands

## Basic Scan

```bash
nmap 192.168.1.10 
```

## Scan Multiple Hosts

```bash
nmap 192.168.1.10 192.168.1.20 
```

## Scan Subnet

```bash nmap 192.168.1.0/24 
```

## Scan Specific Ports

```bash nmap -p 22,80,443 192.168.1.10 
```

## Scan Port Range

```bash nmap -p 1-1000 192.168.1.10 
```

## Service Detection

```bash sudo nmap -sV 192.168.1.10 
```

## Operating System Detection

```bash sudo nmap -O 192.168.1.10 
```

## Aggressive Scan

```bash sudo nmap -A 192.168.1.10 
```

## TCP SYN Scan

```bash sudo nmap -sS 192.168.1.10 
```

## UDP Scan

```bash sudo nmap -sU 192.168.1.10 
```

## Host Discovery Only

```bash nmap -sn 192.168.1.0/24 
```

## Save Results

```bash nmap -A 192.168.1.10 -oN scan.txt 
```

## Save XML Output

```bash nmap -A 192.168.1.10 -oX scan.xml 
```

## Run NSE Scripts

```bash nmap --script default 192.168.1.10 
```

## Vulnerability Scripts

```bash nmap --script vuln 192.168.1.10 
```
