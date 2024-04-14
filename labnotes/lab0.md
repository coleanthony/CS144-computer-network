# Lab Checkpoint 0: networking warmup

## Networking by hand

### 1. Fetch a Web Page

```bash
telnet cs144.keithw.org http
```

It's better to type in the whole content at one time.

```http
GET /hello HTTP/1.1
Host: cs144.keithw.org 
Connection: close
# enter: Sends an empty line
```

```http
HTTP/1.1 200 OK
Date: Sun, 14 Apr 2024 08:07:09 GMT
Server: Apache
Last-Modified: Thu, 13 Dec 2018 15:45:29 GMT
ETag: "e-57ce93446cb64"
Accept-Ranges: bytes
Content-Length: 14
Connection: close
Content-Type: text/plain

Hello, CS144!
```

### 2. Send yourself an email

I have no SUNet ID.

```bash
telnet 148.163.153.234 smtp
Trying 148.163.153.234...
Connected to 148.163.153.234.
Escape character is '^]'.
220 mx0b-00000d03.pphosted.com ESMTP mfa-m0190090
```

```bash
HELO mycomputer.stanford.edu
250 mx0b-00000d03.pphosted.com Hello [36.112.3.117], pleased to meet you
MAIL FROM: sunetid@stanford.edu
250 2.1.0 Sender ok
RCPT TO: sunetid@stanford.edu
550 5.1.1 User Unknown
DATA
503 5.5.1 Need RCPT (recipient)

From: sunetid@stanford.edu
To: sunetid@stanford.edu
Subject: Hello from CS144 Lab 0!
.
500 5.5.1 Command unrecognized: "From: sunetid@stanford.edu"
500 5.5.1 Command unrecognized: "To: sunetid@stanford.edu"
500 5.5.1 Command unrecognized: "Subject: Hello from CS144 Lab 0!"

QUIT
```
### 3. Listening and connecting

```bash
netcat -v -l 9091
Listening on 0.0.0.0 9091
Connection received on localhost 41328
hhh
hello
^C
```

```bash
telnet localhost 9091
Trying 127.0.0.1...
Connected to localhost.
Escape character is '^]'.
hhh
hello
Connection closed by foreign host.
```







