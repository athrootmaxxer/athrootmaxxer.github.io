---
title: "cURL Cheatsheet"
date: 2026-05-29
categories: [Cheatsheets]
tags: [curl, web-security, commands, notes]
---

# cURL Cheatsheet

> Useful cURL commands for Web Security, API testing, and HTTP requests.

---

# Basic Requests

## Basic GET Request

```bash
curl http://example.com
````

Sends a basic HTTP GET request.

---

## Download File

```bash
curl -O http://example.com/index.html
```

Downloads the file/page with the original filename.

---

## Silent Mode

```bash
curl -s -O http://example.com/index.html
```

Uses silent mode to suppress progress output.

---

## Ignore SSL Certificate Check

```bash
curl -k http://example.com
```

Skips SSL/TLS certificate verification.

---

# Viewing Headers & Responses

## Verbose Output

```bash
curl -v http://example.com
```

Displays the full HTTP request and response.

---

## Display Response Headers Only

```bash
curl -I https://www.example.com
```

Sends a HEAD request and shows only response headers.

---

## Display Headers and Response Body

```bash
curl -i https://www.example.com
```

Displays both response headers and response body.

---

# User Agent

## Set Custom User-Agent

```bash
curl https://www.example.com -A 'Mozilla/5.0'
```

Sets a custom User-Agent header.

---

# Authentication

## Add Authorization Header

```bash
curl -H 'Authorization: Basic YWRtaW46YWRtaW4=' http://<SERVER_IP>:<PORT>/
```

Adds a custom Authorization header.

---

## Provide Credentials

### Method 1

```bash
curl -u admin:admin http://<SERVER_IP>:<PORT>/
```

### Method 2

```bash
curl -v http://admin:admin@<SERVER_IP>:<PORT>/
```

Provides credentials directly through the cURL command.

---

# POST Requests

## Send POST Request with Form Data

```bash
curl -X POST -d 'username=admin&password=admin' http://<SERVER_IP>:<PORT>/ -I
```

Sends POST request with form data.

---

# Cookies

## Add Cookie Using -b

```bash
curl -b 'PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1' http://<SERVER_IP>:<PORT>/
```

Adds cookie to the request.

---

## Add Cookie Header Manually

```bash
curl -H 'Cookie: PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1' http://<SERVER_IP>:<PORT>/
```

Adds cookie using the Cookie header.

---

# JSON Requests

## Send JSON Data

```bash
curl -X POST -d '{"search":"london"}' \
-b 'PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1' \
-H 'Content-Type: application/json' \
http://<SERVER_IP>:<PORT>/search.php
```

Sends JSON data with the appropriate Content-Type header.

---

# Notes

This cheatsheet was created while studying the **Web Requests** module from the CWES learning path.

The goal of this page is not just storing commands, but continuously updating it with:
- useful cURL commands
- authentication methods
- request manipulation techniques
- headers, cookies, and JSON requests
- real examples used throughout future modules

As I progress further into CWES and PortSwigger labs, this cheatsheet will continue evolving based on practical usage and things I learn during the journey.

```bash
curl -X GET /knowledge
> 200 OK
```

* `-X` → Specify HTTP method
* `-d` → Send request data
* `-H` → Add custom headers
* `-b` → Send cookies
* `-u` → Provide credentials
* `-v` → Verbose output
* `-I` → Fetch headers only
* `-i` → Include response headers in output
* `-k` → Ignore SSL certificate verification

---

```bash
whoami
> athrootmaxxer
```
