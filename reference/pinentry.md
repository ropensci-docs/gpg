# Password Entry

Function to prompt the user for a password to read a protected private
key.

## Usage

``` r
pinentry(prompt = "Enter your GPG passphrase:")
```

## Arguments

- prompt:

  the string printed when prompting the user for input.

## Details

If available, this function calls the GnuPG `pinentry` program. However
this only works in a terminal. Therefore the IDE can provide a custom
password entry widget by setting the `askpass` option. If no such option
is specified we default to
[`readline`](https://rdrr.io/r/base/readline.html).
