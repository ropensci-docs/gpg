# PGP Signatures

Utilities to create and verify PGP signatures.

## Usage

``` r
gpg_verify(signature, data = NULL, error = TRUE)

gpg_sign(data, signer = NULL, mode = c("detach", "normal", "clear"))
```

## Arguments

- signature:

  path or raw vector for the gpg signature (contains the `PGP SIGNATURE`
  block)

- data:

  path or raw vector with data to sign or verify. In `gpg_verify` this
  should be `NULL` if `signature` is not detached (i.e. `clear` or
  `normal` signature)

- error:

  raise an error if verification fails because you do not have the
  signer public key in your keyring.

- signer:

  (optional) vector with key ID's to use for signing. If `NULL`, GPG
  tries the user default private key.

- mode:

  use `normal` to create a full OpenPGP message containing both data and
  signature or `clear` append the signature to the clear-text data (for
  email messages). Default `detach` only returns the signature itself.

## See also

Other gpg:
[`gpg_encrypt()`](https://docs.ropensci.org/gpg/reference/gpg_encrypt.md),
[`gpg_keygen()`](https://docs.ropensci.org/gpg/reference/gpg_keygen.md),
[`gpg_keys`](https://docs.ropensci.org/gpg/reference/gpg_keys.md)

## Examples

``` r
if (FALSE) { # \dontrun{
# This requires you have the Debian master key in your keyring
msg <- tempfile()
sig <- tempfile()
download.file("http://http.us.debian.org/debian/dists/stable/Release", msg)
download.file("http://http.us.debian.org/debian/dists/stable/Release.gpg", sig)
gpg_verify(sig, msg, error = FALSE)
} # }
```
