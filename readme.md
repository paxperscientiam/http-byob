Under heavy development. Use it at your own peril.

What is?
===
`http-byob` is my little attempt at creating a faux container. All it is, however, is a script for running `dnsmasq` and verstion 2.4 of Apache's `httpd` web server.

I've separated a lot of `httpd` configuration settings into variables stored in the `bash` script `sbin/http-byob`. At some point, I will entirely separate configuration options. Same with `dnsmasq` configuration, eventually.


Requirements:
* `bash`
* `httpd` v2.4
* `dnsmasq`


Usage
===
Oh shoot, I need to add a help menu!

Start:
* `[sudo] sbin/http-byob start`

Stop:
* `[sudo] sbin/http-byob stop`

I decided to use named pipe for handling logging. That way, I think, disk access is limited.

In order to actually watch the logs, do one of the following:
* `sbin/http-byob --watch dns`
* `sbin/http-byob --watch httpd`


If by some miracle you are able to get this to work, this repo includes an example site that you load in your browser:

`www.example.local.dev`


This assumes a directory structure like this (relative to repo):

`www/clients/<SUBDOMAIN>/<DOMAIN.TLD>/wwwroot/`





Note
===
`http-byob` is meant to work offline. Not sure why, but there seems to be an issue with Safari when disconnected from the Internet.



--local-service
Accept DNS queries only from hosts whose address is on a local subnet, ie a subnet for which an interface exists on the server. This option only has effect if there are no --interface --except-interface, --listen-address or --auth-server options. It is intended to be set as a default on installation, to allow unconfigured installations to be useful but also safe from being used for DNS amplification attacks.
