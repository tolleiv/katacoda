# Preparation

## Generating the private key

You can generate a private key with:
`openssl genrsa -des3 -out private.pem 2048`{{execute}}

You'll have to enter a passphrase - as this is a example, use a simple one which you could easily remember.

## Generating the public key

From that private key, export the public key to a file:

`openssl rsa -in private.pem -outform PEM -pubout -out public.pem`{{execute}}

Here you have to reenter the passphrase.

Inspect both keys:

`cat private.pem`{{execute}}

`cat public.pem`{{execute}}

## Keep in mind

**The generated files are base64-encoded encryption keys in plain text format. The private key file is encrypted with your passphrase. Be sure to remember this passphrase and backup your private key or the key pair becomes useless.**
