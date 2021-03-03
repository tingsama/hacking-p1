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



[chrome]: https://github.com/tingsama/hacking-p1/blob/main/images/chrome.png 'Chrome Logo'
[firefox]: https://github.com/tingsama/hacking-p1/blob/main/images/firefox.png 'Firefox Logo'
[safari]: https://github.com/tingsama/hacking-p1/blob/main/images/safari.png 'Safari Logo'
[microsoft]: https://github.com/tingsama/hacking-p1/blob/main/images/microsoft.png 'Microsoft Logo'
[dashlane]: https://github.com/tingsama/hacking-p1/blob/main/images/dashlane.png 'Dashlane Logo'
[keeper]: https://github.com/tingsama/hacking-p1/blob/main/images/keeper.png 'Keeper Logo'
[onepassword]: https://github.com/tingsama/hacking-p1/blob/main/images/chrome.png 'Onepassword Logo'
[keepass]: https://github.com/tingsama/hacking-p1/blob/main/images/keepass.png 'Keepass Logo'
