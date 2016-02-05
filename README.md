_The PS>Attack Built Tool is currently available as an [beta](https://github.com/jaredhaight/psattackbuildtool/releases/). You can also download a pre-built version of the the beta for PS>Attack (the portable environment that this build tool customizes) [here](https://github.com/jaredhaight/PSAttack/releases/)._

_These projects are under heavy, active development. Version 1.0 will be released at this years [CarolinaCon](http://carolinacon.org). I'm writing an ongoing series of articles about where this project is at [here](https://www.psattack.com/tags/psattack/)_

_If you have any questions or suggestions for PS>Attack, feel free to reachout on twitter or via email: jaredhaight `at` prontonmail.com_

## PS>Attack Build Tool [![Build status](https://ci.appveyor.com/api/projects/status/c5v1nxo38a7nec3b?svg=true)](https://ci.appveyor.com/project/jaredhaight/psattack)

A tool that makes it easy to compile a custom version of [PS>Attack](https://github.com/jaredhaight/psattack), a portable powershell attack environment. 

#### What does the PS>Attack Build Tool do?
The build tool downloads the latest version of [PS>Attack](https://www.github.com/jaredhaight/psattack/) and the latest versions of tools that is uses (PowerSploit, Powercat, Inveigh, etc) and encrypts them with a custom key. It then compiles everything, producing a custom version of PS>Attack that's up to date and consists of unique file signatures, making it very difficult for Antivirus and Incident Response teams to find.

#### PS>Attack
PS>Attack is a self contained custom PowerShell console that comes with a lot of the latest and greatest offensive PowerShell tools. It's designed to make it very easy for Pentesters to incorporate PowerShell into their workflow. It's suitable to be used on live engagements as it's capable of evading Antivirus and Incident Response teams with the following tricks.

1. It doesn't rely on powershell.exe. Instead it calls powershell directly through the .NET framework.
2. The modules that are bundled with the exe are encrypted. When PS>Attack starts, they are decrypted into memory. The unencrypted payloads never touch disk, making it difficult for most antivirus engines to find them.
3. When generated by the PS>Attack Build Tool, the payloads are encrypted with a unique key. This means that the generated executable's signature changes each time it's created. 

PS>Attack contains commands for Privilege Escalation, Recon and Data Exfilitration. It does this by including the following modules and commands:
* [Powersploit](https://github.com/PowerShellMafia/PowerSploit)
  - Invoke-Mimikatz
  - Invoke-GPPPassword
  - Invoke-NinjaCopy
  - Invoke-Shellcode
  - Invoke-WMICommand
  - VolumeShadowCopyTools
* [PowerTools](https://github.com/PowerShellEmpire/PowerTools)
  - PowerUp
  - PowerView
* [Nishang](https://github.com/samratashok/nishang)
  - Gupt-Backdoor
  - Do-Exfiltration
  - DNS-TXT-Pwnage
  - Get-Infromation
  - Get-WLAN-Keys
  - Invoke-PsUACme
* [Powercat](https://github.com/besimorhino/powercat)
* [Inveigh](https://github.com/Kevin-Robertson/Inveigh)

It also comes bundled with `get-attack`, a command that allows you to search through the included commands and find the attack that you're looking for.

![Get-Attack](http://i.imgur.com/XKUEvkl.png)

#### Greetz
PS>Attack was inspired by and benefits from a lot of incredible people in the PowerShell community. Particularly [mattifiestation](https://twitter.com/mattifestation) of PowerSploit and [sixdub](https://twitter.com/sixdub), [engima0x3](https://twitter.com/enigma0x3) and [harmj0y](https://twitter.com/HarmJ0y) of Empire. Besides writing the modules and commands that give PS>Attack it's punch, their various projects have inspired alot of my approach to this project as well as my decision to try and contirbute something back to the community.

A huge thank you to [Ben0xA](https://twitter.com/ben0xa), who's [PoshSecFramework](https://github.com/PoshSec/PoshSecFramework) was used to figure out a lot of things about how to build a powershell console.
