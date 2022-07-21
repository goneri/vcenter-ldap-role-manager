# CLI for vSphere 7.0.3 to set group and role to LDAP user

There is no API to set a role or a group to a LDAP/AD user. This CLI uses Selenium to interact with vSphere and register your user.

## Requirements

- `selenium`
- `chromedriver`, `dnf install chromedriver` on Fedora

## Example

Register the user `foobar` add Administrator.

    $ vcenter-ldap-role-manager foobar my-ldap-server --add-role Administrator --add-group Administrators

`my-ldap-server` is the name of your LDAP/AD directory in vSphere.

## Demo

[![demo](https://asciinema.org/a/510116.svg)](https://asciinema.org/a/510116?autoplay=1)

## License

GPLv3+
