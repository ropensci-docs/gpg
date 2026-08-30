# GPG key generation

Generates a new standard private-public keypair. This function is mostly
for testing purposes. Use the `gpg --gen-key` command line utility to
generate an official GPG key with custom fields and options.

## Usage

``` r
gpg_keygen(name, email, passphrase = NULL)
```

## Arguments

- name:

  value for the `Name-Real` field

- email:

  value for the `Name-Email` field

- passphrase:

  (optional) protect with a passphrase

## References

GPG manual section on [Unattended key
generation](https://www.gnupg.org/documentation/manuals/gnupg/Unattended-GPG-key-generation.html).

## See also

Other gpg:
[`gpg_encrypt()`](https://docs.ropensci.org/gpg/reference/gpg_encrypt.md),
[`gpg_keys`](https://docs.ropensci.org/gpg/reference/gpg_keys.md),
[`gpg_sign()`](https://docs.ropensci.org/gpg/reference/gpg_sign.md)
