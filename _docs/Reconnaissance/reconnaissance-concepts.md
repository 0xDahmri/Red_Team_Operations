---
title: Reconnaissance Concepts
category:
order: 1
---

### Interception Proxies

* A software-based proxy that runs on our attack machine that we have configured as an intentional man-in-the-middle (MITM).
* Setup includes running the software and listening on a given port (8080 is defacto for most tools) and having the browser configured to proxy all traffic to 127.0.0.1:8080.
* When on, navigating to &lt;target\_url&gt; the browser will connect to our interception proxy which in turn connects to &lt;target\_url&gt; and the response traffic from the server will come back through the proxy on the way to the server.
* Two popular interception proxies: Burp Suite and ZAP.

### WHOIS Protocol

The major regional registrars run WHOIS servers, as do large ISPs and some other large organizations.

The regional registrar WHOIS servers are:

* whois.afrinic.net (Africa)
* whois.apnic.net (Asia Pacific, India, China, and Australia)
* whois.arin.net (US and Canada)
* whois.lacnic.net (Mexico and Latin America)
* whois.ripe.net (Europe, Greenland, Russia, and the Middle East)

On Linux / Mac from terminal you can simply enter the following to perform a WHOIS lookup:

~~~
$ whois a.b.c.d
~~~

Which returns some useful information such as names, phone numbers, physical address, and DNS servers.&nbsp; Note that due to GDPR some records may be scrubbed.

### DNS

DNS is the Domain Name System, a global hierarchical database of domain names.

The majority of DNS operates via UDP on port 53.&nbsp; Most zone transfers occur via TCP port 53 because they are larger than 512 bytes.&nbsp; A zone transfer is just the download of a DNS zone or database of names for a given domain or subdomain.&nbsp; Some sites block TCP port 53 in an effort to stop DNS zone transfers.

An example of performing a full (AXFR) zone transfer via dig:

~~~
$ dig website.com -t axfr
~~~

&nbsp;

&nbsp;
