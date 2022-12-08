OAuth2 PAM module
=================

This PAM module enables login with OAuth2 token instead of password.
This is a fork from [CyberDem0n/pam-oauth2](https://github.com/CyberDem0n/pam-oauth2) module, but instead of using a token information endpoint it uses the standard OAuth2 introspection endpoint [rfc7662](https://www.rfc-editor.org/rfc/rfc7662).

## How to install it:

```bash
$ sudo apt-get install libcurl4-openssl-dev libpam-dev
$ git submodule init
$ git submodule update
$ make
$ sudo make install
```

## Configuration

```
auth sufficient pam_oauth2.so <introspection_endpoint> <login field> active=true iss=<token_issues>
```

> **_NOTE:_** It is important to do a active=true check according to the rfc7662.

License
-------

This project uses the [MIT license](https://raw.githubusercontent.com/pgstenberg/pam-oauth2/master/LICENSE).
