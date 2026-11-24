# Lab 02: TCP Three-Way Handshake Analysis

## 1. Objective
Understand how TCP establishes a connection between a client and a server.

## 2. Lab Environment

| Device | IP Address |
|---|---|
| Kali Linux | 192.168.250.10 |
| Metasploitable 2 | 192.168.250.20 |

Target Service: FTP  
Target Port: 21

## 3. Tools Used
- Kali Linux
- Wireshark
- Netcat (nc)

## 4. Command Used

```bash
nc -vz 192.168.250.20 21
```

Result:

```text
192.168.250.20: inverse host lookup failed: Unknown host
(UNKNOWN) [192.168.250.20] 21 (ftp) open
```

## 5. Wireshark Filter

```text
tcp.port == 21
```

## 6. Three-Way Handshake

### Step 1: SYN
- Source IP: 192.168.250.10
- Destination IP: 192.168.250.20
- Source Port: 52566
- Destination Port: 21
- SYN = 1
- ACK = 0
- Relative Sequence Number = 0

### Step 2: SYN-ACK
- Source IP: 192.168.250.20
- Destination IP: 192.168.250.10
- SYN = 1
- ACK = 1
- Relative Sequence Number = 0
- Relative Acknowledgment Number = 1

### Step 3: ACK
- Source IP: 192.168.250.10
- Destination IP: 192.168.250.20
- ACK = 1
- Relative Sequence Number = 1
- Relative Acknowledgment Number = 1

## 7. Important TCP Concepts
- SYN: Initiates a TCP connection.
- SYN-ACK: Acknowledges the request and responds.
- ACK: Confirms the server response.
- Sequence Number: Tracks transmitted data.
- Acknowledgment Number: Indicates the next expected sequence number.

## 8. Conclusion
The TCP three-way handshake was successfully observed in Wireshark, and the FTP service on port 21 was confirmed reachable.

## 9. Lessons Learned
- Understanding TCP connection establishment.
- Identifying SYN, SYN-ACK, and ACK packets.
- Reading TCP sequence and acknowledgment numbers.
- Using Wireshark to inspect TCP connections.
