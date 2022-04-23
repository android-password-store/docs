# Bugs related to OpenKeychain not launching

If you clicked a password entry but the screen did not show its contents or ask for your GPG key's passphrase, you might be facing an operating system bug that's common with XiaoMi and Nokia devices.

Following the steps for XiaoMi from [here](https://dontkillmyapp.com/xiaomi), or for Nokia from [here](https://dontkillmyapp.com/nokia) should alleviate the problem. The steps for XiaoMi devices are reproduced here because it appears to be the overwhelming majority of users facing this bug.

- Enable the `Display pop-up windows while running in the background` permission for OpenKeychain from the Settings app
- Enable the 'Autostart' permission from the same screen if it's shown

On some devices the screen may be hidden deep in the Settings app, the navigation path in that case is ` Settings -> Apps -> Permissions -> Other Permissions -> OpenKeychain`.

