# Task 2 — Directory Enumeration

## Objective

The objective of this task was to discover directories and files present on the designated vulnerable web application using directory enumeration.

## Introduction

Directory enumeration is a web reconnaissance technique used to discover files, directories, and other resources that may not be directly visible from the main website.

Web applications can contain different directories such as:

/admin
/uploads
/images
/cgi-bin

Some of these resources may not be linked from the main webpage but can still exist on the server.

Directory enumeration helps a security analyst understand the structure of a web application and identify resources that may require further investigation.

## Tool Used

Gobuster / Dirbuster

These tools are used for directory and file enumeration by sending requests to a web server using a list of commonly used file and directory names.

## Target

Target: testphp.vulnweb.com

The target was the designated vulnerable web application provided for the internship exercise.

## Methodology

The assessment followed these steps:

* Identify the target web application.
* Perform directory and file enumeration.
* Analyze the HTTP status codes returned by the server.
* Identify accessible and restricted resources.
* Analyze the discovered resources from a security perspective.

## Command Used

Directory enumeration was performed against the target web application using a wordlist.

## Command Explanation

The enumeration tool checks different file and directory names from the wordlist by sending HTTP requests to the target.

For example:

/admin
/uploads
/test
/cgi-bin

The server responds with an HTTP status code for each request. These status codes help determine whether the requested resource exists and whether it can be accessed.

## Results

The following resources were discovered:

/crossdomain.xml -> 200
/CVS/Entries -> 200
/favicon.ico -> 200
/index.php -> 200
/pictures/ -> 301
/secured/ -> 301
/vendor/ -> 301
/cgi-bin/ -> 403

## Result Analysis

The discovered resources returned different HTTP status codes.

200 -> The requested resource was accessible.

/crossdomain.xml -> Accessible
/CVS/Entries -> Accessible
/favicon.ico -> Accessible
/index.php -> Accessible

301 -> The requested resource exists and the server redirected the request.

/pictures/ -> Redirected
/secured/ -> Redirected
/vendor/ -> Redirected

403 -> The resource exists or the server recognizes the requested path, but access is forbidden.

/cgi-bin/ -> Access forbidden

A 403 response does not automatically mean that the resource is vulnerable. It indicates that access to the resource is restricted.

## Security Significance

Directory enumeration can reveal resources that are not directly visible through the main website.

Some discovered files or directories may contain sensitive information, administrative functionality, backup files, configuration files, or other resources that should not be publicly accessible.

Therefore, discovered paths should be investigated carefully during a security assessment.

The general process is:

Discover Resource -> Check Status Code -> Identify Purpose -> Check Access -> Investigate Security Risk

## Limitations

- Directory enumeration depends on the wordlist being used.
- Resources with names not present in the wordlist may not be discovered.
- Some servers may block or rate-limit enumeration requests.
- A discovered resource does not automatically mean that a vulnerability exists.
- HTTP status codes need to be interpreted in the context of the application.

## Key Learnings

- Learned what directory enumeration is.
- Understood how web directories and files can be discovered.
- Learned the purpose of using wordlists during enumeration.
- Learned the meaning of common HTTP status codes such as 200, 301, and 403.
- Understood that a 403 response can indicate a restricted resource.
- Learned how directory enumeration helps identify the attack surface of a web application.

## Conclusion

This task helped me understand how directory enumeration can be used to discover files and directories present on a web application.

Several accessible, redirected, and restricted resources were identified during the enumeration process. This showed how directory enumeration can provide useful information about the structure and exposed resources of a web application.

