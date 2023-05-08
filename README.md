# ip-address-email

`ip-address-email` is a basic script that keeps track of the current external IP address of a system.  If the address changes it sends and e-mail notification to designated recipients.

This is useful when you have a system behind a router on which the external IP address may change, such as with consumer broadband routers which are typically assigned dynamic IP addresses.


## Requirements

* mailutils
* working MTA such as Postfix


## Setup
```bash
cp ip-address-email /usr/local/bin/

# add recipient e-mail addresses to 
# recipients= line in /usr/local/bin/ip-address-email
# multiple addresses can be given, separated by commas (with no spaces)

# create the file where the IP address is stored
touch /var/cache/ip_address
```

### cron setup

create `/etc/cron.d/ip-address-email` with the contents:
```crontab
0            *          *    *   *  root    /usr/local/bin/ip-address-email
```


