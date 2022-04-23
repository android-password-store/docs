# What is an invalid GPG key ID and how to fix it?

The `pass` CLI uses the `.gpg-id` file as a way to identify which GPG key to use for creating new passwords. For a while we didn't use this, and instead asked users to manually select a key to encrypt with. As noted in the changelog [here](https://msfjarvis.dev/posts/aps-july-release/#proper-support-for-per-directory-keys), this made it impossible to support per-directory keys.

However, because of that change we now rely on being able to parse the myriad formats of GPG key IDs into formats that OpenKeychain can understand. This succeeds for most people, but if you're among the few unlucky ones where it fails with "Found .gpg-id, but it contains an invalid key ID, fingerprint or user ID"; it is easy to fix that.

Make sure you are on v1.13.2 or newer of APS, then go to Settings > "Show hidden files and folders" and enable it. Go back to the password list, and delete the `.gpg-id` file. You can now go back and disable the "Show hidden files and folders" option. When you next create a password, you will be taken to OpenKeychain to select a GPG key which will then be written into the `.gpg-id` file in a format that both OpenKeychain and GPG can understand.
