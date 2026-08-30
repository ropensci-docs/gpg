# GPG keyring management

Signing or encrypting with GPG require that the keys are stored in your
personal keyring. Use
[gpg_version](https://docs.ropensci.org/gpg/reference/gpg_info.md) to
see which keyring (home dir) you are using. Also see
[gpg_keygen](https://docs.ropensci.org/gpg/reference/gpg_keygen.md) for
generating a new key.

## Usage

``` r
gpg_import(file)

gpg_recv(id, search = NULL, keyserver = NULL)

gpg_send(id, keyserver = NULL)

gpg_delete(id, secret = FALSE)

gpg_export(id, secret = FALSE)

gpg_list_keys(search = "", secret = FALSE)

gpg_list_signatures(id)
```

## Arguments

- file:

  path to the key file or raw vector with key data

- id:

  unique ID of the pubkey to import (starts with `0x`). Alternatively
  you can specify a `search` string.

- search:

  string with name or email address to match the key info.

- keyserver:

  address of http keyserver. Default behavior is to try several commonly
  used servers (MIT, Ubuntu, GnuPG, Surfnet)

- secret:

  set to `TRUE` to list/export/delete private (secret) keys

## See also

Other gpg:
[`gpg_encrypt()`](https://docs.ropensci.org/gpg/reference/gpg_encrypt.md),
[`gpg_keygen()`](https://docs.ropensci.org/gpg/reference/gpg_keygen.md),
[`gpg_sign()`](https://docs.ropensci.org/gpg/reference/gpg_sign.md)

## Examples

``` r
if (FALSE) { # \dontrun{
# Submit key to a specific key server.
gpg_send("87CC261267801A17", "https://keys.openpgp.org")
# Submit key to many key servers.
gpg_send("87CC261267801A17")
} # }
```
