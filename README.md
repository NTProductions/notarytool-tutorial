# notarytool-tutorial
 How to use notarytool to code sign

## Important First Run Setup
```xcrun notarytool store-credentials --apple-id "appleidemail" --team-id "asc-provider"```
##### Example
```xcrun notarytool store-credentials --apple-id "ntproductionstest@gmail.com" --team-id "377KTRNNCY"```
### Enter a profile name for later 
```NTProductions```
### Enter <a src="https://support.apple.com/en-us/HT204397">app-specifc password</a>
```aaaa-bbbb-cccc-dddd```
##### Upon Success
```
Validating your credentials...
Success. Credentials validated.
Credentials saved to Keychain.
```

## Notarize is now EZ
```xcrun notarytool submit <pathToFile> --keychain-profile "profilename" --wait```
##### Example
``` xcrun notarytool submit /Users/fromage/Documents/myPlugin/Products/@rpath/My\ WiPlugin.zip --keychain-profile "NTProductions" --wait```
### Upon Success
```
Upload progress: 100.00% (22.4 KB of 22.4 KB)   
Successfully uploaded file

Waiting for processing to complete.
Current status: In Progress...

Processing complete
  id: aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee
  status: Accepted
```

## Now just staple like usual
```xcrun stapler staple <pathToFile>```