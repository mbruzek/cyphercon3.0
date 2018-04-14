# Developer Friendly Cryptography

Presenter: Brice Williams (bricex)
Date: 04/13/2018

Brice works at SysLogic Inc. a company that reviews other company's code for
application security and correct usage of encryption. Offers training and
guidance.

"If you think cryptography is the answer to your problem then you don't know
what your problem is" - Dr. Peter G. Neumann

Observations from the field:  
* Weak password storage
* Use of reversible encryption
* Not using salt
* Poor key management
* Keys not stored correctly
* Lack of granular key usage and key rotation

They have seen all kinds of bad uses.
* Obfuscation by moving bits is not encryption.
* Bad random number seed (don't use the MAC address).
* Overly complex encryption schemes are usually a red flag.
* Random values should never be stored next to encrypted data.

Why are mistakes so common? Developers have challenges:  
1. It needs to work first
2. Delivery dates
3. Performance or usability concerns
4. Inadequate security testing
5. Lack of developer training

Online sources lack practical uses of cryptography. Or do not use Authenticated
Cryptography. No mention of kernel based RNG (instead of userspace RNG). Too
many choices, of encryption algorithms.

ECC > RSA in most cases.
Don't use broken ciphers!
Developers should read the
[OAuth 2.0 Threat Model and Security Considerations](https://tools.ietf.org/html/rfc6819)
RFC.

Should the developers stop doing cryptography and leave that to the Security
professionals? Maybe, but not likely going to happen.

### Use Developer friendly Cryptography

No need to select ciphers or key sizes, have the library pick the good ones by
default. Automatic generation of encryption key, initialization and salt values.
No low security options!

Recommended libraries:
* libsodium - Very good multiple language bindings.
* libhydrogen - Written in C99 used for embedded systems.
* monocypher
* Tink
* ASP.NET core - Microsoft only

Key management best practices:
* No key/secret should be in clear text!
* Keys should have a limited lifetime
* Keys should be rotated automatically
* There should be a method to revoke keys
* All key events should be audited/logged

Good implementations:  
* Hashicorp Vault (gold standard)
* KeyWhiz

Recommendations:
* Use TLS
* Storage Encryption solutions (so everything is encrypted at rest)
* Developer friendly crypto libraries (libsodium)
* Key mangement software for production, test, and development environments.

https://download.libsodium.org/doc/
https://github.com/jedisct1/libhydrogen
https://www.vaultproject.io/
