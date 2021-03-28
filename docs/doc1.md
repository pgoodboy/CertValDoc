---
id: doc1
title: Official Web Application
sidebar_label: Web App Tutorial
---

Usage of our [Official Web Application](https://oatpejoycertval.netlify.app/)

## Main menu

Our Official Web Application requires no knowledge of coding in any language, consist of 4 functions

![](/img/official/main_menu.jpg "Main menu")

## Web Regist
![](/img/official/regist_name.png "Web Regist")

This is not a necessary function, yet a very useful function. It maps your input URL to your public key. When you add a certificate and someone verifies it, the website will return your input URL as the certificate adder's URL. It's totally fine if you don't map your URL to your public key. It's just a function that make's users more convenient.

To map your URL, you just basically need to put the URL you want to be shown in the input box and submit. You can change your URL any time. Just remember any time you make a transaction, it costs you gas fee.

## Regist Cert
![](/img/official/regist_cert.png "Regist Cert")

To add a certificate file to our system, you can either browse for the file or drag the file and drop it in our box then press submit. The application will calculate the hash of the file and stores it in Blockchain.

## Validate Cert
![](/img/official/validate.png "Validate Cert")

If you are someone who want to validate whether a certificate file is genuine and the information has not been tampered, this function is for you.
If the certificate is found on the blockchain, it will return the certificate information.

To validate a certificate, you need to upload the certificate file and the public key of the association you believe they issued the certificate e.g. You beleive a certificate is issued by Bob's University so you need to put Bob's University(The associate needs to broadcast their public key.) 

## Revoke/Unrevoke Cert
![](/img/official/toggle.png "Toggle Cert")

This function is used to toggle the certificate's status from usable to revoked and vice versa.

To toggle a certificate's status, you need to upload the certificate file and fill your confirm text. The confirm text is the file's name without the extension e.g. we only fill "Hello" if the full file name is "Hello.txt"

The transaction will be processed if only your account is the same account as the one who added the certificate to the system.
