# Encrypting messages with the public key

Messages can be encrypted with the public key. The only person who's able to decrypt these messages is the owner of the related private key. Using keys this way, we can ensure the identity of the receiver.

## Encrypting a file:

Create a file with some content:

`echo 'too many secrets' > file.txt`{{execute}}

Encrypt it with the public key:

`openssl rsautl -encrypt -inkey public.pem -pubin -in file.txt -out file.encrypted`{{execute}}

## Transport

Usually the encrypted message would now travel from sender to a remote receiver. It content is kept *relatively* secure during that transport.

## Decrypting the file

Decrypt it with the private key:

`openssl rsautl -decrypt -inkey private.pem -in file.encrypted -out decrypted.txt`{{execute}}

Check the result:

`cat decrypted.txt`{{execute}}
