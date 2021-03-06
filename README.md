# Password Managers (KeePass)

### Why Password Managers
- You don’t need to remember hundreds of passwords
- You only need to remember one master password
- You can have different passwords for different websites and don't need to worry about forgeting them

### Popular Password Managers[1]
| In-browser based | Commercial based |
| --------         | --------         |
| Google Chrome ![alt text][chrome]      | Dashlane ![alt text][dashlane]      |
| Mozilla Firefox ![alt text][firefox]   | Keeper ![alt text][keeper]          |
| Safari ![alt text][safari]             | 1Password ![alt text][onepassword]    |
| Microsoft Edge ![alt text][microsoft]  | KeePass ![alt text][keepass]        |

### Password Managers Workflow
![][work_flow]

#### [Difference between automatic autofill and manual autofill](https://medium.com/@brianrusseldavis/are-autofill-password-managers-safe-8805edf952bf#:~:text=The%20Difference%20Between%20These%20Two%20Types%20of%20Autofill&text=According%20to%20a%20recent%20study,another%20to%20submit%20the%20credentials)
##### Automatic Autofill:
- Does not wait for user interaction
- One click: submit button 
- Vulnerable to vatious sweep attacks
##### Manual Autofill:
- Wait for user interaction 
- Two clicks: select correct account + submit credential 
- More secure 

### Threats, Attacks and Defences
##### [Redirect Sweep Attacks](https://www.usenix.org/conference/usenixsecurity14/technical-sessions/presentation/silver)
- Resirect sweep attack is only gainst automatic autofill password managers. When a taget user connect to a wifi hotspot that is controlled by an attacker, the attacker will trick the password manager to fillin the password and send the password back to the attacker.[2]
- Defence:
  - Require user interaction before autofilling 
  - Login page over HTTPS
##### [Cross Site Scripting(XSS) Injection](https://cispa.saarland/group/stock/papers/stock2014protecting.pdf)
- An attacker inject JavaScript code to login page then the program gets credentials and send back to the attacker.[3]
- Defence:
  - Explicit user interaction to trigger fill-in action
  - URL matching and form matching
##### [Other Attacks](https://www.usenix.org/system/files/conference/usenixsecurity14/sec14-paper-silver.pdf)
- iFrame sweep attack
- Window sweep attack
- Attack amplification via password sync


### Keepass 
[download KeePass](https://keepass.info/)
##### Why Keepass
- Third party tool
- Manual autofill (secure)
- Free and open-source 
- Strong compatibility (it primarily used in Windows devices, but it supports all Operating Systems like Mac, IOS, Android, Linux)[4]
- Lightweight (it wouldn’t occupy many memory of your device)
- Easy to use (it has clear User Interface, so it would be easy-to-manage even for the beginner)
##### How Keepass works
- The KeePass stores all the passwords in _a database file_, which is locked with _a master key_. [5]
- The database file is encrypted using the _best_ and _most secure_ encryption algorithms, which are __AES__ and __Twofish__.
- KeePass uses __SHA-256__ to hash the master key components.
##### Encryption algorithms
##### [AES](https://securityboulevard.com/2020/04/advanced-encryption-standard-aes-what-it-is-and-how-it-works/)
![alt text][AES] 
- It uses __symmetric block cipher__
- It proved to be useful to protect sensitive data
  - __National Security Agency (NSA)__ utilize AES encryption to protect their sensitive information [6]
  - __Many governments and institutions__ are using AES to protect their data [7]
- It __hard to brute force__, since it accepts key sizes more than 128 bits
##### [Twofish](https://www.schneier.com/academic/archives/1998/12/the_twofish_encrypti.html)
![alt text][Twofish] 
- It uses __symmetric block cipher__
- It Trade-offs between __key-setup time__ and __encryption speed__ that make it unique among the AES candidates [8]
- There have been a few attacks on Twofish. However, It did __not constitute a true cryptanalysis__ [9], according to its creator, Bruce Schneier.
- It __hard to brute force__. Similar to AES, since the TwoFish supports key sizes of more than 256 bits, it is resistant to brute force attack[10]
##### [SHA-256](https://www.solarwindsmsp.com/blog/sha-256-encryption#:~:text=SHA%2D256%20is%20a%20patented,that%20is%20256%20bits%20long.&text=In%20cryptographic%20hashing%2C%20the%20hashed,its%20original%20512%2Dbit%20form)
![alt text][SHA-256] 
- SHA-256 is a __patented cryptographic hash function__
- It is a __keyless hash function__ that takes information and generates random characters with __length 256 bits__ [11]
- It is almost impossible to reconstruct the initial data from the hash value.
  - A brute-force attack would need to make 2256 attempts to generate the initial data. [12]
- It is unlikely to have two same hash value of two inputs.
  - With 2256 possible hash values, the likelihood of two being the same is infinitesimally, unimaginably small. [12]
- The avalanche effect.
  - A minor change to the original data will make its hash value change a lot. So two similar inputs will not likely generates similar hashed output through AHS-256.
##### KeePass Demo
- [How to use KeePass](https://www.youtube.com/watch?v=ckYeD7yYJn0)



### References
[1] D. Balaban, “Comparing In-Browser-Based, Commercial Password Managers,” eWEEK, 18-Feb-2021. [Online]. Available: https://www.eweek.com/search-engines/comparing-in-browser-based-commercial-password-managers/. [Accessed: 03-Mar-2021].<br />
[2]D. Silver, S. Jana, and D. Boneh, “Password Manager: Attacks and Defenses,” 23rd USENIX Security Symposium, Aug 20 - 22, 2014.<br />
[3] “Preventing XSS Attacks through CSS Whitelisting,” Powered by MediaWiki. [Online]. Available: https://www.mediawiki.org/wiki/Preventing_XSS_Attacks_through_CSS_Whitelisting. [Accessed: 03-Mar-2021].<br />
[4]“Managing my passwords with KeePass and OwnCloud,” Managing my passwords with KeePass and OwnCloud | Gabriel's Tech blog. [Online]. Available: https://www.detassigny.net/posts/3/managing-my-passwords-with-keepass-and-owncloud. [Accessed: 03-Mar-2021].<br />
[5]D. Reichl, KeePass Password Safe. [Online]. Available: https://keepass.info/. [Accessed: 03-Mar-2021].<br />
[6] M. from R. Thomas, R. Thomas, Eyal Gruner | 3 days ago, Kyle Marchini | 4 days ago, Y. E. | F. 23, Richi Jennings | 1 day ago, R. J. | F. 22, and R. J. | F. 19, “Advanced Encryption Standard (AES): What It Is and How It Works,” Security Boulevard, 24-Apr-2020. [Online]. Available: https://securityboulevard.com/2020/04/advanced-encryption-standard-aes-what-it-is-and-how-it-works/. [Accessed: 03-Mar-2021].<br />
[7] M. Cobb, “What is AES Encryption and How Does it Work?,” SearchSecurity ,17-Apr-2020. [Online]. Available:https://searchsecurity.techtarget.com/definition/Advanced-Encryption-Standard#:~:text=TheAdvanced Encryption Standard (AES,cybersecurity and electronic data protection.[Accessed: 03-Mar-2021].<br />
[8]B. Schneier, Schneier on Security. [Online]. Available: https://www.schneier.com/academic/archives/1998/12/the_twofish_encrypti.html. [Accessed: 03-Mar-2021].<br />
[9]S. Encrypt, “Twofish Encryption: What Is It?,” Choose To Encrypt, 07-Mar-2019. [Online]. Available: https://choosetoencrypt.com/tech/twofish-encryption/. [Accessed: 03-Mar-2021].<br />
[10]D. Miladinović and R. R. Rosario, “Twofish vs AES Encryption,” Cloudstorageinfo.org, 22-Dec-2020. [Online]. Available: https://cloudstorageinfo.org/twofish-vs-aes-encryption. [Accessed: 03-Mar-2021].<br />
[11]“SHA-256 Algorithm Overview,” Solarwinds MSP, 26-Jan-2021. [Online]. Available: https://www.solarwindsmsp.com/blog/sha-256-encryption#:~:text=SHA-256 is a patented,that is 256 bits long.&text=In cryptographic hashing, the hashed,its original 512-bit form. [Accessed: 03-Mar-2021].<br />
[12]f4tca7, “Introduction to the SHA-256 hash function,” Steemit. [Online]. Available: https://steemit.com/cryptocurrency/@f4tca7/introduction-to-the-sha-256-hash-function. [Accessed: 03-Mar-2021].<br />




[chrome]: https://github.com/tingsama/hacking-p1/blob/main/images/chrome.png 'Chrome Logo'
[firefox]: https://github.com/tingsama/hacking-p1/blob/main/images/firefox.png 'Firefox Logo'
[safari]: https://github.com/tingsama/hacking-p1/blob/main/images/safari.png 'Safari Logo'
[microsoft]: https://github.com/tingsama/hacking-p1/blob/main/images/microsoft.png 'Microsoft Logo'
[dashlane]: https://github.com/tingsama/hacking-p1/blob/main/images/dashlane.png 'Dashlane Logo'
[keeper]: https://github.com/tingsama/hacking-p1/blob/main/images/keeper.png 'Keeper Logo'
[onepassword]: https://github.com/tingsama/hacking-p1/blob/main/images/onepassword.png 'Onepassword Logo'
[keepass]: https://github.com/tingsama/hacking-p1/blob/main/images/keepass.png 'Keepass Logo'
[AES]: https://github.com/tingsama/hacking-p1/blob/main/images/AES.png 'AES Workflow'
[Twofish]: https://github.com/tingsama/hacking-p1/blob/main/images/Twofish.png 'Twofish Workflow'
[SHA-256]: https://github.com/tingsama/hacking-p1/blob/main/images/SHA-256.png 'SHA-256 Workflow'
[work_flow]:https://github.com/tingsama/hacking-p1/blob/main/images/work_flow.png 'password manager Work_flow'

