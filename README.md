# dns_cpaneldns

This script is a plugin for acme.sh found in te repository https://github.com/Neilpang/acme.sh to add TXT verificationrecords to CPanel's DNS for Letsencrypt certificates. In general, before you start issueing a new certificate, you have to set a few variables for this plugin once. These variables can be found in the first lines of the script.

These are:
* CPANELDNS_AUTH_ID = Your CPanel's User ID
* CPANELDNS_AUTH_PASSWORD = Your CPanels User ID password
* CPANELDNS_API = Your Cpanels web adress including portnumber, mostly 2083

These one-time set variables will be saved for later use in the configuration of acme.sh.
See: https://github.com/Neilpang/acme.sh/tree/master/dnsapi for the a general idear.

## Usage
Before you start using acme.sh with this plugin you have to set the following variables once and only on first use:

```
export CPANELDNS_AUTH_ID="MY_Account"
export CPANELDNS_AUTH_PASSWORD="My_Password"
export CPANELDNS_API="https://www.example.com:2083/"
```

Copy this dns_cpaneldns script in a subdirectory below acme.sh with the name 'dnsapi'.
Then execute:

```
acme.sh --issue --dns dns_cpaneldns -d example.com -d www.example.com
```

Have Fun!
