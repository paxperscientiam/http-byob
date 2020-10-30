# DISCLAIMER: THIS SCRIPT IS EXPERIMENTAL. YOU USE IT AT YOUR OWN PERIL.

![](demo.gif
)
## Quick test

``` shell
# clone in $HOME folder
cd ~
git clone git@github.com:paxperscientiam/http-byob.git
cd http-byob
./sbin/http-byob start --root .
```
Confirm that things are working well by going here: http://localhost:80/server-info


## Build your own
``` shell
cd ~
# This will create the folder ${HOME}/HTTP-BYOB_Container and scaffold there
http-byob build --root # this will
http-byob start --root # start httpd and dnsmasq
```
Confirm that things are working well by going here: http://localhost:80/server-info


## Tearing down ...
``` shell
cd ~
http-byob stop --root # stop httpd and dnsmasq
\rm HTTP-BYOB_Container # this will remove everyting ... duh
```

OK, let's say you create a container with name.

``` shell
cd ~
http-byob build --root ./custom-container-name
```

When you do this, you can go forth one of two ways ...

``` shell
# cd into the container and specify --root as .
# or, stay above the container directory and specify --root as path/to/custom-container-name
```

## Going further

* https://github.com/FiloSottile/mkcert


<!-- Under heavy development. Use it at your own peril. -->



<!-- What is? -->
<!-- === -->
<!-- `http-byob` is my little attempt at creating a faux container. All it is, however, is a script for running `dnsmasq` and verstion 2.4 of Apache's `httpd` web server. -->

<!-- I've separated a lot of `httpd` configuration settings into variables stored in the `bash` script `sbin/http-byob`. At some point, I will entirely separate configuration options. Same with `dnsmasq` configuration, eventually. -->


<!-- Requirements: -->
<!-- * `bash` -->
<!-- * `httpd` v2.4 -->
<!-- * `dnsmasq` -->


<!-- Usage -->
<!-- === -->
<!-- Oh shoot, I need to add a help menu! -->

<!-- Start: -->
<!-- * `[sudo] sbin/http-byob start` -->

<!-- Stop: -->
<!-- * `[sudo] sbin/http-byob stop` -->

<!-- I decided to use named pipe for handling logging. That way, I think, disk access is limited. -->

<!-- In order to actually watch the logs, do one of the following: -->
<!-- * `sbin/http-byob --watch dns` -->
<!-- * `sbin/http-byob --watch httpd` -->


<!-- If by some miracle you are able to get this to work, this repo includes an example site that you load in your browser: -->

<!-- `www.example.org.lan` -->


<!-- This assumes a directory structure like this (relative to repo): -->

<!-- `www/clients/<SUBDOMAIN>/<DOMAIN.TLD>/wwwroot/` -->





<!-- Note -->
<!-- === -->
<!-- `http-byob` is meant to work offline. Not sure why, but there seems to be an issue with Safari when disconnected from the Internet. -->



<!-- --local-service -->
<!-- Accept DNS queries only from hosts whose address is on a local subnet, ie a subnet for which an interface exists on the server. This option only has effect if there are no --interface --except-interface, --listen-address or --auth-server options. It is intended to be set as a default on installation, to allow unconfigured installations to be useful but also safe from being used for DNS amplification attacks. -->
