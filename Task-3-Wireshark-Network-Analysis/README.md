# Task 3 — Wireshark Network Analysis

## Objective

The objective of this task was to capture and analyze network traffic using Wireshark and identify information transferred through HTTP communication.

## Introduction

Wireshark is a network protocol analyzer used to capture and analyze network packets.

When a device communicates with a web server, the communication is divided into packets and transmitted through the network.

Wireshark allows a security analyst to inspect these packets and understand what is happening during network communication.

In this task, HTTP traffic was analyzed while interacting with the login page of the designated vulnerable web application.

## Tool Used

Wireshark

Wireshark is a network protocol analyzer that captures network traffic and allows packets to be inspected at different protocol layers.

It can be used to analyze protocols such as:

TCP
UDP
HTTP
DNS
TLS

## Target

Target: testphp.vulnweb.com

The target was the designated vulnerable web application provided for the internship exercise.

## Methodology

The assessment followed these steps:

- Open Wireshark and start capturing network traffic.
- Access the login page of the target web application.
- Generate HTTP traffic by interacting with the login page.
- Apply the HTTP display filter.
- Identify the HTTP requests related to the login process.
- Inspect the packet contents and transferred information.
- Analyze the security implications of the observed traffic.

## Wireshark Filter Used

```text
http
```

The http filter was used to display HTTP-related packets and make it easier to identify web requests and responses.

## Packet Analysis

During the capture, HTTP packets generated while interacting with the login page were observed.

The HTTP communication contained application-level information that could be inspected directly from the captured packets.

The login request was identified by examining the HTTP request packets.

Wireshark can also be used to follow the communication between the client and server using the TCP stream associated with the packets.

## Result Analysis

The captured traffic showed communication between the client and the web server over HTTP.

HTTP does not provide encryption for the application data being transmitted.

Because of this, sensitive information sent through an HTTP connection may be visible to someone who is able to capture the network traffic.

This demonstrates why secure applications should use HTTPS instead of plain HTTP when transmitting sensitive information.

## Security Significance

Analyzing network traffic is an important part of security monitoring and incident investigation.

If sensitive information is transmitted over an unencrypted protocol such as HTTP, an attacker who can capture the traffic may be able to inspect the transmitted data.

This is why HTTPS is important for protecting web communication.

The general process is:

Capture Traffic -> Apply Filter -> Identify Communication -> Inspect Packets -> Analyze Security Impact

## Limitations

- Wireshark can only analyze traffic that is captured on the available network interface.
- Encrypted traffic such as HTTPS cannot normally be read directly as plain application data.
- Packet analysis can become difficult when a large amount of network traffic is captured.
- The `http` filter only displays HTTP-related traffic and does not show every packet involved in the complete communication.

## Key Learnings

- Learned the basic purpose of Wireshark.
- Learned how network traffic is captured and analyzed.
- Learned how display filters can be used to find specific protocol traffic.
- Learned how to identify HTTP requests and responses.
- Learned how TCP communication can be analyzed using packet streams.
- Understood the security risks of transmitting sensitive information over HTTP.
- Learned why HTTPS is important for protecting web communication.

## Conclusion

This task helped me understand how Wireshark can be used to capture and analyze network traffic.

By analyzing HTTP traffic generated during interaction with the login page, I was able to identify the communication between the client and web server and understand the security implic

