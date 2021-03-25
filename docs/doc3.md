---
id: doc3
title: Smart Contract
sidebar_label: Smart Contract
---

We don't use database. We use Blockchain instead because it is Decentralized !

In case you don't want to use our [Official Web App](doc1.md) or our [API](doc2.md), you can directly connect to our Smart Contract.

See our full Smart contract on [Github](https://github.com/Krow18D/DigitalCertValidate/blob/drizzle/contracts/Poe.sol)
## Connect to Smart Contract

Our Smart Contract is deployed at `https://rinkeby.infura.io/v3/b7a05df5e4ff4c05b767ad142933054e` but you can also download it from [Github](https://github.com/Krow18D/DigitalCertValidate/blob/drizzle/contracts/Poe.sol) and deploy it on your local machine.

## Hash Validation
`isValidHash(string memory hash) private pure returns (bool)`

This function takes an input of a `hash string` and returns the checking result as a `boolean`. It checks whether the hash is in `SHA512` format or not. If the hash string is in the SHA512 format, it returns `true` or else it returns `false`

We don't normally directly call the function itself. But it is used to verify in `addCertificate` function.

## URL mapper
`mapAdder(string memory schoolName)`

This function takes an `input string`(which is intended to be the URL of the school.) It then maps the input string to the `public key` of the caller.

## Add Certificate

`addCertificate(string memory hash)`

This function takes an input of a `hash string` and stores `status`(default as `true`), adder's `public key`, `time`, ` Block number` to Blockchain.
It then emits event `Added(hash, msg.sender)`

We use this function to store new certificate's hashe into Blockchain.

## Validate Certificate
`findCertificate(string memory hash) public view returns (bool,address,uint256,uint256,string memory)`

This function takes an input of a `hash string` and finds if the hash exist in Blockchain. If the hash exists, it returns `status`, adder's `public key`, `time`, ` Block number` of the certificate.

We usually compare the returned public key to the public key of the association which is clamed to be the certificate issuer. If they match, the certificate is literally added by the claimed associate.
The status is also useful in case of certificate revokation which can be done by using `toggleStatus` function

## Toggle Certificate Status

`toggleStatus(string memory hash)`

This function takes an input of a `hash string` and checks if the caller has the same `address` as the account who added the certificate. If the address match, the `status` of the certificate will be changed(from `true` to `false` and vice versa.)