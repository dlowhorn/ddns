# dlowhorn/ddns

## NAME
ddns_puship - Push the current IP address to the specified DNS record

## SYNOPSIS
ddns_puship [OPTIONS] [PATH TO CONFIG FILE]

## DESCRIPTION
Push the current IP address to the specified DNS record
       
With no FILE, assume config is in PWD/dns.conf

-v show verbose debugging output
 
# SETUP
Copy cloudflare.conf.sample to cloudflare.conf and fill in with desired account/domain info

# SAMPLE CONFIG
```
CLOUDFLARE_EMAIL="<Cloudflare account email address>"
ZONE_IDENTIFIER="<DNS Zone, available on your Cloudflare DNS Overview page, right column >"
API_KEY="<Generate your global API token key at https://dash.cloudflare.com/profile/api-tokens>"
DOMAIN_NAME="<The domain you wish to update to this machine's IP address>"
PROXIED=<true|false>
DNS_RECORD_TYPE="<The type (e.g., A) of the DNS record you wish to update>"
```
# SYSTEM INTEGRATION
Cloudflare's API usage limits are detailed at https://developers.cloudflare.com/fundamentals/api/reference/limits/
Unless you are using the API elsewhere, you should have no issues setting up a system timer or cronjob to run on boot 
and/or however often you like #to keep your current IP address registered as the home of your indicated domain.

