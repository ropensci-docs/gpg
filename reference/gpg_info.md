# Manage the GPG engine

Use `gpg_restart()` to find the `gpg` program and home directory (which
contains configuration and keychains). Usually the default should be
fine and you do not need to run this function manually.

## Usage

``` r
gpg_restart(home = NULL, path = NULL, debug = "none", silent = FALSE)

gpg_version(silent = FALSE)

gpg_info()

gpg_options()
```

## Arguments

- home:

  path to your GPG configuration directory (including keyrings)

- path:

  location of `gpg` or `gpg2` or `gpgconf` or (on windows)
  `gpgme-w32spawn.exe`

- debug:

  debugging level, integer between 1 and 9

- silent:

  suppress output of `gpg --version`

## Details

Use `gpg_info()` to get your current engine settings. The
`gpg_version()` function simply calls `gpg --version` to see some
verbose output about the `gpg` executable.

`gpg_options` reads options in the GnuPG configuration file, which is
stored by default in `~/.gnupg/gpg.conf`. Note that changing options
might affect other software using GnuPG.

## Examples

``` r
gpg_version()
#> gpg (GnuPG) 2.4.4
#> libgcrypt 1.10.3
#> Copyright (C) 2024 g10 Code GmbH
#> License GNU GPL-3.0-or-later <https://gnu.org/licenses/gpl.html>
#> This is free software: you are free to change and redistribute it.
#> There is NO WARRANTY, to the extent permitted by law.
#> 
#> Home: /github/home/.gnupg
#> Supported algorithms:
#> Pubkey: RSA, ELG, DSA, ECDH, ECDSA, EDDSA
#> Cipher: IDEA, 3DES, CAST5, BLOWFISH, AES, AES192, AES256, TWOFISH,
#>         CAMELLIA128, CAMELLIA192, CAMELLIA256
#> Hash: SHA1, RIPEMD160, SHA256, SHA384, SHA512, SHA224
#> Compression: Uncompressed, ZIP, ZLIB, BZIP2
gpg_info()
#> $gpgconf
#> [1] "/usr/bin/gpgconf"
#> 
#> $gpg
#> [1] "/usr/bin/gpg"
#> 
#> $version
#> [1] ‘2.4.4’
#> 
#> $home
#> [1] "/github/home/.gnupg"
#> 
#> $gpgme
#> [1] ‘1.18.0’
#> 
```
