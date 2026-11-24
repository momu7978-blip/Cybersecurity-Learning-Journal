# Lab 01: ICMP Traffic Analysis Using Wireshark

## 1. Objective
Understand how ICMP Echo Request and Echo Reply packets work and analyze them using Wireshark.

## 2. Lab Environment

| Device | IP Address |
|---|---|
| Kali Linux | 192.168.250.10 |
| Metasploitable 2 | 192.168.250.20 |

Network: VMware Host-Only  
Interface: eth1

## 3. Tools Used
- Kali Linux
- Wireshark
- ping

## 4. Commands

Start packet capture on eth1, then execute:

```bash
ping -c 4 192.168.250.20
```

Wireshark display filter:

```text
icmp
```

## 5. Observations

### Echo Request
- ICMP Type: 8
- Code: 0
- TTL: 64

### Echo Reply
- ICMP Type: 0
- Code: 0
- TTL: 64

### Round Trip Time
Observed RTT: 0.766569 ms

## 6. Analysis
- Echo Request is sent from Kali to Metasploitable.
- Echo Reply is returned by Metasploitable.
- Type 8 identifies an Echo Request.
- Type 0 identifies an Echo Reply.
- TTL indicates the remaining packet lifetime.
- RTT measures the round-trip time.

## 7. Conclusion
The experiment successfully demonstrated ICMP communication between two virtual machines and showed how Wireshark can be used to inspect network packets.

## 8. Lessons Learned
- Understanding ICMP packet types.
- Identifying request and reply packets.
- Reading TTL and RTT values.
- Applying Wireshark display filters.
