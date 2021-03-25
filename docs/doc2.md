---
id: doc2
title: API Usage
---

## Calculate hash of file

Takes input as a `file` and returns `SHA512` hash of the file.

```
POST /getHash

Requires : form-data:
{
file (file upload)
}
```
`Response : Hash String`


## Register Certificate

Takes input as a `file` and adder's `Private key`, then returns the transaction result.
```
POST /registcert
Requires : form-data:
{
file (file upload) ,
pvk (private key to do transactions)
}
```
`Response : Transaction Result`

## Certificate Validation

First, takes input as a `file` and `Public key` of account who is beleived to be the adder. Next, queries the adder of the file in Blockchain. Then, compare with the input Public key. Finally returns result whether the adder in Blockchain and the input Public key matches or not.

```
POST /validatecert
Requires : form-data:
{
file (file upload) ,
pubkey (Adder's public key for checking with result)
}
```
`Response : Certificate's information in smart contract`

## Revoke/Unrevoke Certificate

Takes input as a file and adder's `Private key`. If the input Private key is the key pair of the `Public key` in Blockchain, the certificate `status` changes.
```
POST /togglecert
Requires : form-data:
{
file (file upload) ,
pvk (private key to do transactions)
}
```
`Response : Transaction Result`

## Register name

This function takes an `link` and `Private key`. It then maps the `link` to the `Public key` of the caller.

```
POST /registweb
Requires : form-data:
{
link (url that contain show your public key and will show in certificate's
information) ,
pvk (private key to do transactions)
}
```
`Response : Register result`