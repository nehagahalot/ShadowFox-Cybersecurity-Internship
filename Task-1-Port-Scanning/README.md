# Task 1 — Port Scanning

## Objective

The objective of this task was to identify the open ports and running services on the designated vulnerable web application using Nmap.

## Introduction

Port scanning is a network reconnaissance technique used to determine which ports on a host are accessible and whether services are listening on those ports.

A host can expose multiple network services through different ports. For example:

Port 22 -> SSH
Port 80 -> HTTP
Port 443 -> HTTPS

Identifying open ports helps a security analyst understand the externally exposed attack surface of a system.

An important distinction is that an open port does not automatically indicate a vulnerability. It indicates that a service is accessible and may require further investigation.

## Tool Used

Nmap (Network Mapper)

Nmap is a network scanning and security auditing tool used to discover hosts, identify open ports, detect services, and perform service/version detection.

## Target

Target: testphp.vulnweb.com

Resolved IP: 44.228.249.3

The target was the designated vulnerable web application provided for the internship exercise.

## Methodology

The assessment followed these steps:

- Identify the IP address of the target.
- Perform a port scan against the target.
- Identify the open ports.
- Detect the services associated with the open ports.
- Analyze the results from a security perspective.

## Command Used

nmap -sV 44.228.249.3

## Command Explanation

nmap:Starts the Nmap scanner
-sV: Enables service and version detection
44.228.249.3: IP address of the target

The -sV option instructs Nmap to probe discovered ports to determine which services are running and, where possible, identify their versions.

## Results

The scan identified the following open service:

80/tcp -> open -> HTTP

## Result Analysis

Port 80 was found to be open on the target.

Port 80 is commonly used for HTTP traffic. The scan identified an HTTP service running on this port.

Here:

80 -> Port number

TCP -> Transport protocol

Open -> A service is accepting connections on the port

HTTP -> Detected service


## Security Significance

An open port means that a service is accessible on the target and therefore becomes part of its exposed attack surface.

However, an open port does not automatically mean that the system is vulnerable. The service running on the port needs to be investigated further.

The general process is:

Open Port -> Identify Service -> Identify Version -> Check Configuration -> Look for Vulnerabilities

## Limitations

- A port scan only provides information about the exposed services.
- An open port does not by itself prove that a vulnerability exists.
- Service and version detection may not always be completely accurate.
- Scan results can change depending on firewall rules, network conditions, and the current state of the target.

## Key Learnings
- Learned the purpose of network port scanning.
- Understood the difference between an IP address, port, and service.
- Learned how Nmap identifies open ports.
- Learned how the -sV option performs service/version detection.
- Learned that an open port is an exposure point, not automatically a vulnerability.
- Learned how port scanning forms the initial stage of network reconnaissance.

## Conclusion

This task helped me understand how Nmap can be used to identify open ports and the services running on them.

The scan identified TCP port 80 as open and running an HTTP service. Through this task, I learned how port scanning can be used as an initial step to understand the exposed services of a target system.
