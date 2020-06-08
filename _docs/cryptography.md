# Cryptography

## Issue

After searching and discussing to find solution for the issue [https://tule-developer.gitbook.io/noway/\_docs/store-apis-key-in-frontend-sdk-issues](https://tule-developer.gitbook.io/noway/_docs/store-apis-key-in-frontend-sdk-issues)  
We decided using Secret Key Cyptography. The key will be stored in the customer backend

## Ref

I found a an good overview of Cryptography here [https://www.garykessler.net/library/crypto.html](https://www.garykessler.net/library/crypto.html)  


## Brief of cryptography types

There are 3 types

* _Secret Key Cryptography \(SKC\): Uses a single key for both encryption and decryption; also called symmetric encryption. Primarily used for privacy and confidentiality._

  -&gt; Using this method for server-server communication, the key will be store in the server, so it will be protected



* _Public Key Cryptography \(PKC\): Uses one key for encryption and another for decryption; also called asymmetric encryption. Primarily used for authentication, non-repudiation, and key exchange._

  -&gt; Using for exchange info between 1 - n communication, for example: chat, establishing secure communications over the Internet ssl,..



* _Hash Functions: Uses a mathematical transformation to irreversibly "encrypt" information, providing a digital fingerprint. Primarily used for message integrity._

  -&gt; Using for checking data integrity, for excample: check sum for data request

##  

