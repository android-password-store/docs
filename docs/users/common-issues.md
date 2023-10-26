# Common issues

When you are installing APS you can encounter some issues based on your setup, the most common of them are given below with their fixes.

## OpenKeychain failed to launch

Many OEMs create excessive limitations on background apps to "improve" battery life by breaking normal functionality, the workarounds for those are described [here](https://docs.passwordstore.app/docs/users/background-killing-bugs).


# "Error reading input data" [#2653](https://github.com/android-password-store/android-password-store/issues/2653), [#2179](https://github.com/android-password-store/android-password-store/issues/2179)

OpenKeychain doesn't support AEAD encryption (default in gpg 2.3+). Dropping the OCB option from the key's preference string fixes the issue

```plaintext
$ gpg --edit-key <key-id>

gpg> showpref
  [ultimate] (1).name <email>
  Cipher: AES256, AES192, AES, 3DES
  AEAD: OCB
  Digest: SHA512, SHA384, SHA256, SHA224, SHA1
  Compression: ZLIB, BZIP2, ZIP, Uncompressed
  Features: MDC, AEAD, Keyserver no-modify
gpg> setpref AES256 AES192 AES 3DES SHA512 SHA384 SHA256 SHA224 SHA1 ZLIB BZIP2 ZIP
  Set preference list to: Cipher: AES256, AES192, AES, 3DES AEAD: Digest: SHA512, SHA384, SHA256, SHA224, SHA1 Compression: ZLIB, BZIP2, ZIP, Uncompressed Features: MDC, Keyserver no-modify
  Really update the preferences? (y/N) y 
gpg> save

$ pass init <key-id>
```

## "No encrypted data with known key found in stream with newer gopass secrets" [#1530](https://github.com/android-password-store/android-password-store/issues/1530), [#173](https://github.com/android-password-store/android-password-store/issues/173)

This issue caused by option "throw-keyids" which isn't supported by OpenKeychain. To resolve this, you can disable it in two ways:
  1. Reinit your password storage by command with disabling option "throw-keyids" `PASSWORD_STORE_GPG_OPTS="--no-throw-keyids" pass init $KEYID`
  2. Edit your gpg config and set `--no-throw-keyids` in it.
