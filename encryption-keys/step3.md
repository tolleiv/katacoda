# Sign messages with the private key

Often times you want to ensure that message is authentic, that it's coming from a specific sender and that it's content wasn't modified during transport. This can be done with signatures.

## Generating the signature

Generating a signature can be done with:
`openssl dgst -sha256 -sign private.pem -out /tmp/sign.sha256 file.txt`{{execute}}

For convenience this is usually encoded with base64:
`openssl base64 -in /tmp/sign.sha256 -out file.signature`{{execute}}

Inspect the signature:
`cat file.signature`{{execute}}

## Transport

In "normal" communication flows the `file.txt` and the related `file.signature` would now travel from the sender to the receiver. Keep in mind that the content message itself is not protected anyhow and on an insecure channel everyone could still read the content.

## Verify a signature

`openssl base64 -d -in file.signature -out /tmp/sign.sha256`{{execute}}

`openssl dgst -sha256 -verify public.pem -signature /tmp/sign.sha256 file.txt`{{execute}}

This should usually show you sth like: `Verified OK` and confirm that the file.

Using a manipulated `file.txt` would show `Verification Failure`:

`echo "manipulation" >> file.txt`{{execute}}
`openssl dgst -sha256 -verify public.pem -signature /tmp/sign.sha256 file.txt`{{execute}}




