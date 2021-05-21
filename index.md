# PLAY CTF and CHANGE YOUR LIFE

# HASHES

## JOHN THE RIPPER

_john --format=[format] --wordlist=[path to wordlist] [path to file]_
 
 **NTHash / NTLM** 

You can acquire NTHash/NTLM hashes by dumping the SAM database on a Windows machine, by using a tool like Mimikatz or from the Active Directory database: NTDS.dit. You may not have to crack the hash to continue privilege escalation- as you can often conduct a "pass the hash" attack instead, but sometimes hash cracking is a viable option if there is a weak password policy.

**Cracking Hashes from /etc/shadow** 

_unshadow [path to passwd] [path to shadow]_

**SINGLE CRACK MODE**

Single Crack mode. In this mode, John uses only the information provided in the username, to try and work out possible passwords heuristically, by slightly changing the letters and numbers contained within the username.

_john --single --format=[format] [path to file]_

**A Note on File Formats in Single Crack Mode:**

If you're cracking hashes in single crack mode, you need to change the file format that you're feeding john for it to understand what data to create a wordlist from. You do this by prepending the hash with the username that the hash belongs to, so according to the above example- we would change the file hashes.txt

**What are Custom Rules?**

Custom rules are defined in the john.conf file, usually located in /etc/john/john.conf [Wordlist rules syntax.]  (https://www.openwall.com/john/doc/RULES.shtml)

_john --wordlist=[path to wordlist] --rule=PoloPassword [path to file]_

**Zip2John**

use John to crack the password on password protected Zip files.

_zip2john [options] [zip file] > [output file]_

_john --wordlist=/usr/share/wordlists/rockyou.txt zip_hash.txt_

**Rar2John**

obtain the password for rar archives.

_rar2john [rar file] > [output file]_

_john --wordlist=/usr/share/wordlists/rockyou.txt rar_hash.txt_

**SSH2John**

_ssh2john [id_rsa private key file] > [output file]_
_john --wordlist=/usr/share/wordlists/rockyou.txt id_rsa_hash.txt_





 
 


