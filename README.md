# Password Managers (KeePass)

### Why Password Managers
- You don’t need to remember hundred passwords
- You don’t need to worry about forgetting passwords 
- You only need to remember one master password

### Popular Password Managers
| In-broswer based | Commercial based |
| --------         | --------         |
| Google Chrome ![alt text][chrome]      | Dashlane ![alt text][dashlane]      |
| Mozilla Firefox ![alt text][firefox]   | Keeper ![alt text][keeper]          |
| Safari ![alt text][safari]             | 1Password ![alt text][onepassword]    |
| Microsoft Edge ![alt text][microsoft]  | KeePass ![alt text][keepass]        |

### Password Managers Workflow
##### Automatic Autofill:
- Does not wait for user interaction
- One click: submit button 
- Vulnerable to vatious sweep attacks
##### Manual Autofill:
- Wait for user interaction 
- Two clicks: select correct account + submit credential 
- More secure 

### Threats, Attacks and Defences
##### Redirect Sweep Attacks
- Against automatic autofill password managers
- Targer user connect to a WiFi hotspot controlled by an attacker
- Defence:
  - Require user interaction before autofilling 
  - Login page over HTTPS
##### Cross Site Scripting(XSS) Injection
- An attacker inject JavaScript code to login page 
- Get credentials and send back to the attacker 
- Defence:
  - Explicit user interaction to trigger fill-in action
  - URL matching and form matching


###### read more about password managers attack and defence
- [presentation by David Silver, Password Managers: Attacks and Defenses](https://www.usenix.org/conference/usenixsecurity14/technical-sessions/presentation/silver)
- [paper by David Silver, Password Managers: Attacks and Defenses](https://www.usenix.org/system/files/conference/usenixsecurity14/sec14-paper-silver.pdf)
- [Protecting Users Against XSS-based Password Manager Abuse ](https://cispa.saarland/group/stock/papers/stock2014protecting.pdf)



### Keepass 
##### Why Keepass
- Third party tool
- Manual autofill (secure)
- Free and open-source 
- Strong compatibility (it primarily used in Windows devices, but it supports all Operating Systems like Mac, IOS, Android, Linux)
- Lightweight (it wouldn’t occupy many memory of your device)
- Easy to use (it has clear User Interface, so it would be easy-to-manage even for the beginner)
##### How Keepass works
- The KeePass stores all the passwords in _a database file_, which is locked with _a master key_. [reference k1]
- The database file is encrypted using the _best_ and _most secure_ encryption algorithms, which are __AES__ and __Twofish__.
- KeePass uses __SHA-256__ to hash the master key components.
##### AES
- It uses __symmetric block cipher__
- It proved to be useful to protect sensitive data
  - __National Security Agency (NSA)__ utilize AES encryption to protect their sensitive information [reference k2]
  - __Many governments and institutions__ are using AES to protect their data [reference k3]
- It __hard to brute force__, since it accepts key sizes more than 128 bits
##### Twofish
- It uses __symmetric block cipher__
- It Trade-offs between __key-setup time__ and __encryption speed__ that make it unique among the AES candidates [reference k4]
- There have been a few attacks on Twofish. However, It did __not constitute a true cryptanalysis__ [reference k5], according to its creator, Bruce Schneier.
- It __hard to brute force__. Similar to AES, since the TwoFish supports key sizes of more than 256 bits, it is resistant to brute force attack
##### SHA-256
- SHA-256 is a __patented cryptographic hash function__
- It is a __keyless hash function__ that takes information and generates random characters with __length 256 bits__ [reference k6]
##### KeePass Demo








[chrome]: https://github.com/tingsama/hacking-p1/blob/main/images/chrome.png 'Chrome Logo'
[firefox]: https://github.com/tingsama/hacking-p1/blob/main/images/firefox.png 'Firefox Logo'
[safari]: https://github.com/tingsama/hacking-p1/blob/main/images/safari.png 'Safari Logo'
[microsoft]: https://github.com/tingsama/hacking-p1/blob/main/images/microsoft.png 'Microsoft Logo'
[dashlane]: https://github.com/tingsama/hacking-p1/blob/main/images/dashlane.png 'Dashlane Logo'
[keeper]: https://github.com/tingsama/hacking-p1/blob/main/images/keeper.png 'Keeper Logo'
[onepassword]: https://github.com/tingsama/hacking-p1/blob/main/images/onepassword.png 'Onepassword Logo'
[keepass]: https://github.com/tingsama/hacking-p1/blob/main/images/keepass.png 'Keepass Logo'
[reference k1]: https://keepass.info/
[reference k2]: https://securityboulevard.com/2020/04/advanced-encryption-standard-aes-what-it-is-and-how-it-works/ 
[reference k3]: https://searchsecurity.techtarget.com/definition/Advanced-Encryption-Standard#:~:text=The%20Advanced%20Encryption%20Standard%20
[reference k4]: https://www.schneier.com/academic/archives/1998/12/the_twofish_encrypti.html
[reference k5]: https://choosetoencrypt.com/tech/twofish-encryption/
[reference k6]: https://www.solarwindsmsp.com/blog/sha-256-encryption#:~:text=SHA%2D256%20is%20a%20patented,that%20is%20256%20bits%20long.&text=In%20cryptographic%20hashing%2C%20the%20hashed,its%20original%20512%2Dbit%20form.




