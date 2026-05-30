# Incident Report — HTTP Traffic Analysis

## Analyst Information
- Name: Roony
- Date: 2026-05-30
- Tool Used: Wireshark, tcpdump

## Incident Summary
Captured and analyzed HTTP traffic between local machine and example.com

## Findings

### Packet 1-3: TCP Handshake
- Source: Local machine
- Destination: example.com (port 80)
- Action: Normal TCP connection established (SYN, SYN-ACK, ACK)

### Packet 4: HTTP Request
- Method: GET /
- Host: example.com
- User-Agent: curl/8.18.0
- This identifies the client tool used to make the request

### Packet 7: HTTP Response
- Status: 200 OK
- Content-Type: text/html
- Server returned the homepage successfully

### Packet 10-12: Connection Closed
- FIN packets exchanged
- Connection closed cleanly by both sides

## Conclusion
Traffic appears normal. No suspicious activity detected.
The User-Agent (curl) is expected since we initiated the request manually.

## What Would Be Suspicious
- Unknown or fake User-Agent strings
- Requests to unusual ports
- Large data transfers to external IPs
- Repeated requests in short time (could indicate automated attack)
