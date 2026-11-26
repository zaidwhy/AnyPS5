# libSceLibreSsl

## change [X509_STORE_add_crl]

- [X509_STORE_add_crl](../../../core/libs/prx/libSceLibreSsl/src/X509Store.cpp) - not measured on a PS5. No store lock is taken, and an issuer name is compared through its stored canonical encoding without re-encoding a modified name. Ordering by issuer name, the refusal of a CRL with the same issuer and SHA-1 hash and the reference count follow LibreSSL 2.5.4 [`x509_lu.c`](https://github.com/libressl/openbsd/blob/2e2c612066aa993717528a0249c15c51128d61cb/src/lib/libcrypto/x509/x509_lu.c#L385-L426) and [`x509_cmp.c`](https://github.com/libressl/openbsd/blob/2e2c612066aa993717528a0249c15c51128d61cb/src/lib/libcrypto/x509/x509_cmp.c#L133-L145).
