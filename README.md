# CLI for vSphere 7.0.3 to set group and role to LDAP user

There is no API to set a role or a group to a LDAP/AD user. This CLI uses Selenium to interact with vSphere and register your user.

## Requirements

- `selenium`:
    - `pip install selenium` in a Python virtual env
    - `dnf install python3-selenium` on Fedora

- `chromedriver`, `dnf install chromedriver` on Fedora


## Usage

```
usage: vcenter-ldap-role-manager [-h] [--debug] [--vmware-host VMWARE_HOST] [--vmware-user VMWARE_USER] [--vmware-password VMWARE_PASSWORD] [--headless] [--ignore-ssl-errors] [--add-group ADD_GROUP] [--add-role ADD_ROLE] username domain

vSphere - Add AD/LDAP user to group and role

positional arguments:
  username              User name
  domain                The domain name

options:
  -h, --help            show this help message and exit
  --debug               Expose more information in the console.
  --vmware-host VMWARE_HOST
                        vSphere host, default is to use VMWARE_HOST environment variable
  --vmware-user VMWARE_USER
                        vSphere username, default is to use VMWARE_USER environment variable
  --vmware-password VMWARE_PASSWORD
                        vSphere password, default is to use VMWARE_PASSWORD environment variable
  --headless            Hide the broswer window.
  --ignore-ssl-errors   Ignore the SSL errors with the vSphere server.
  --add-group ADD_GROUP
                        Group to add the user to, e.g: Administrators
  --add-role ADD_ROLE   Role to add the user to, e.g: Administrator
```

## Example

Register the user `foobar` add Administrator.

    $ vcenter-ldap-role-manager foobar my-ldap-server --add-role Administrator --add-group Administrators

`my-ldap-server` is the name of your LDAP/AD directory in vSphere.

## Demo

[![demo](https://asciinema.org/a/510116.svg)](https://asciinema.org/a/510116?autoplay=1)

## Disclaimer

This tool interacts with vSphere web interface directly, because of that, it is likely to break with new vSphere release.

## License

GPLv3+
