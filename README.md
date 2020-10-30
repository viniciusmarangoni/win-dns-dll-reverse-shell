## Summary

This is a Visual Studio project which aims to compile a DLL compatible with Windows DNS server DLL plugin format.

This is used to abuse the DNS Admins privileges in order to get high privilege shell on the Domain Controller. As you can see in the IppSec youtube video mentioned in `References` section, this source code produces a DLL that creates a thread to handle the reverse shell. This results in a DLL that doesnt' kill the DNS server. 


## References

The source code of this project was modified based on the following references:

- Base project: https://github.com/dim0x69/dns-exe-persistance

- Guide from IppSec: https://www.youtube.com/watch?v=8KJebvmd1Fk&feature=youtu.be&t=3130

- Reverse shell in C: https://github.com/tudorthe1ntruder/reverse-shell-poc

- Moving laterally to DC by abusing DNS Admins account: https://www.ired.team/offensive-security-experiments/active-directory-kerberos-abuse/from-dnsadmins-to-system-to-domain-compromise


## How to use this repository

If you want to compile this project, follow below guide:

1 - Install VisualStudio Community: https://visualstudio.microsoft.com/vs/community/

2 - Open Visual Studion, go to `Tools` -> `Get Tools and Features` -> `Individual Components`. Search for and install `MFC for latest` and install its `x86 & x64` version

3 - Download this project and open `dns-plugindll-vcpp/Win32Project1.sln` file

4 - Change IP address and port number of reverse shell in `reverse.cpp` file

5 - Change the dropdown value in VisualStudio to `Release`

6 - Go to `Project` -> `Win32Project1` -> `Configuration Properties` -> `Advanced` and check value of `Use of MFC`. It must be set to `Use MFC in a Static Library`

7 - Click in `Build` -> `Rebuild Solution`


You should see an output in the console similar to the following:

```
Finished generating code
Win32Project1.vcxproj -> C:\Users\aduserb\Desktop\dll-shell\dns-exe-persistance-master\dns-plugindll-vcpp\x64\Release\Win32Project1.dll
========== Rebuild All: 1 succeeded, 0 failed, 0 skipped ==========
```
