# Encryption

Encrypt or decrypt a message using the public key from the `receiver`.
Optionally the message can be signed using the private key of the
sender.

## Usage

``` r
gpg_encrypt(data, receiver, signer = NULL)

gpg_decrypt(data, verify = TRUE, as_text = TRUE)
```

## Arguments

- data:

  path or raw vector with data to encrypt / decrypt

- receiver:

  key id(s) or fingerprint(s) for recepient(s)

- signer:

  (optional) key id(s) or fingerprint(s) for the sender(s) to sign the
  message

- verify:

  automatically checks that all signatures (if any) can be verified and
  raises an error otherwise

- as_text:

  convert output to text. Set to FALSE if you expect binary data.

## See also

Other gpg:
[`gpg_keygen()`](https://docs.ropensci.org/gpg/reference/gpg_keygen.md),
[`gpg_keys`](https://docs.ropensci.org/gpg/reference/gpg_keys.md),
[`gpg_sign()`](https://docs.ropensci.org/gpg/reference/gpg_sign.md)
