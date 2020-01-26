# Snifer-DNS

DNS-Sniffer will quickly scan your network and then display all the DNS queries sent on your system.This allows us to Track the victims activity and perform some useful Recon.
The Domain Name System (DNS) is the phonebook of the Internet. Humans access information online through domain names
  
Setup
=====
  
```
sudo apt-get install python-scapy
```
  
Help
====
  
```
python dns_sniffer.py -h
```

Examples of Use
===============

```
sudo python dns_sniffer.py
```
  
For a specific interface :  
```
sudo python dns_sniffer.py -i eth0
```
  
If you want to log in a database :  
```
sudo python dns_sniffer.py -d db.sqlite
sudo python dns_sniffer.py -d db.sqlite -i eth0
```
or with quiet  
```
sudo python dns_sniffer.py -d db.sqlite -q
sudo python dns_sniffer.py -d db.sqlite -i eth0 -q
```
  
Export the sqlite database to CSV :  
```
sudo python dns_sniffer.py -d db.sqlite -e db.csv
```


Examples of ouput
=================
  
When you open Firefox :  
```
$ sudo python dns_sniffer.py
IP source       | DNS server      | Count DNS request | Query
192.168.13.37
                  192.168.13.254
                                    1                   www.mozilla.org.
                                    1                   snippets.cdn.mozilla.net.
                                    1                   location.services.mozilla.com.
                                    3                   ff.search.yahoo.com.
                                    1                   ocsp.digicert.com.
                                    1                   geo.mozilla.org.
                                    3                   search.yahoo.com.
                                    1                   self-repair.mozilla.org.
                                    1                   ciscobinary.openh264.org.
                                    1                   clients1.google.com.
                                    1                   search.services.mozilla.com.
                                    1                   safebrowsing.google.com.
                                    1                   aus4.mozilla.org.
                                    53                  safebrowsing-cache.google.com.
                  
```
  
When you use a local DNS cache :  
```
$ sudo python dns_sniffer.py
IP source       | DNS server      | Count DNS request | Query
127.0.0.1
                  127.0.1.1
                                    26                  icons.duckduckgo.com.
                                    79                  secure.mywot.com.
                                    14                  code.activestate.com.
                                    200                 r.duckduckgo.com.
                                    234                 ocsp.comodoca.com.
                                    34                  ads.activestate.com.
                  127.0.0.1
                                    26                  icons.duckduckgo.com.
                                    82                  secure.mywot.com.
                                    6                   ecirtam.net.
                                    14                  code.activestate.com.
                                    198                 r.duckduckgo.com.
                                    2                   www.google.com.
                                    235                 ocsp.comodoca.com.
                                    37                  ads.activestate.com.
192.168.13.37
                  192.168.1.254
                                    1                   icons.duckduckgo.com.
                                    2                   secure.mywot.com.
                                    1                   code.activestate.com.
                                    3                   r.duckduckgo.com.
                                    3                   ocsp.comodoca.com.
                                    1                   ads.activestate.com.



