# Common issues
When you are installing APS you can encounter with some issues and troubles, the most common of them are here.
- Issue: "Appearing for a moment" and all issues connected with OpenKeychain, when this app won't work in the background. #518 If you clicked a password entry, but the screen did not show its content or ask for your GPG key's passphrase, you might be facing an operating system bug that's common with XiaoMi and Nokia devices. Following the steps for XiaoMi from here, or Nokia from should alleviate the problem. The steps for XiaoMi devices are reproduced here because it appears to be the overwhelming majority of users facing this bug.
  - Enable the Display pop-up windows while running in the backgroud permission for OpenKeychain from the Settings app
  - Enable the "Autostart" permission from the same screen if it's shown
  - On some devices the screen may be hidden deep in the Settings app, the navigation path in that case is Settings -> Apps -> Permissions -> Other Permissions -> OpenKeychain
- Issue: "Error reading input data" #2653, #2179
  - OpenKeychain doesn't support AEAD encryption (default in gpg 2.3+). Dropping the OCB option from the key's preference string also fixed the issue:
    - `$ gpg --edit-key <key-id> gpg> showpref [ultimate] (1).name <email>     Cipher: AES256, AES192, AES, 3DES     AEAD: OCB     Digest: SHA512, SHA384, SHA256, SHA224, SHA1     Compression: ZLIB, BZIP2, ZIP, Uncompressed     Features: MDC, AEAD, Keyserver no-modify gpg> setpref AES256 AES192 AES 3DES SHA512 SHA384 SHA256 SHA224 SHA1 ZLIB BZIP2 ZIP Set preference list to: Cipher: AES256, AES192, AES, 3DES AEAD: Digest: SHA512, SHA384, SHA256, SHA224, SHA1 Compression: ZLIB, BZIP2, ZIP, Uncompressed Features: MDC, Keyserver no-modify Really update the preferences? (y/N) y gpg> save $ pass init <key-id>`
- Issue: "No encrypted data with known key found in stream with newer gopass secrets" #1530, #173
  - This issue caused by option "throw-keyids" and apparently this option isn't supported by OpenKeychain. Solve this issue you can in two ways:
    - First: reinit your password storage by command with disabling option "throw-keyids" `PASSWORD_STORE_GPG_OPTS="--no-throw-keyids" pass init $KEYID`
    - Second: edit your gpg config and set `--no-throw-keyids` in it.
