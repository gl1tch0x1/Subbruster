# Subbuster

An automation tool developed in bash, for brusting down the subdomain of any website.

<div align="center">
  <img src="image/subbuster.png" width="80%" height="80%">
  <br><small>Ease your automate in recon.{Developed in Bash}</small>
  </div>

# What is Subbuster ?

Subbruster is an automation tool for hunting down the domains & subdomains gathering wheather for single or multiple targets. Subbruster uses multiple tools for doing the subdomains & domians gathering job in a perfect way, it can take a domains / targets list and doing the whole operation on them and after finshing the job it save the result in a comprehandable & ordered way.

After the Subbruster finishes gathering subdomains & domains it filters them from the repeated subdomains & domains then filters the only live subdomains. It also use multiple methods to gather subdomains like: gathering subdomains through github searching [requires github token] also from enumerating wordlist based and other effective techniques.

This tool made & developed to work in Debian based Linux systems & have been tested on:

- Kali Linux

And it should work in other security distributions like:

- ParrotOS
- BackBox
- Kali-Linux

## Subdomains & Domains Gathering:

- Sublist3r

- Amass
  - Enum
    - Passive Mode
  - Intel
    - Whois Mode

- Github-Search
  - Gathering Subdomains Through Github Searching

- Knockpy
  - Deep mode
    - Gather much domains & subdomains through DNS, HTTP & HTTPS requests 
  - Fast mode
    - Gather much domains & subdomains through DNS requests only

- subfinder

- gobuster
  - enumerating subdomains through wordlist

## Filtering Results:

- Unuique result filtering.
- Unique & live result filtering:
  - httpx

# Installation:

1- Simply change the installation script permession to executable mode then run it:

```
chmod +x install && ./install
```
```
chmod +x subbruster && ./subbruster -t <Target>
```

# Usage:

`-t`: This option is to set the target which [single domains] to gather it's subdomains

`-l`: This option is to specify a domains list to gather their subdomains [in the list every domain in a single line] such as:

```
example.com
domains.com
target.com
```

`-d` This option refers to the deep mode in knockpy tool, so to activate the deep scanning mode just use it like `-d true`

`-f` This option refers to the fast mode in knockpy ttol, so to activate the fast scanning mode just use it like `-f true`

`-w` This option is to set a wordlist for the gobuster tool, just use it like `-w <wordlist_path>`

`-g` This option is to set a github token for github subdomain gathering mode, use it like `-g <github_token>`

 `-i` This option is to ignore directory splitting while scanning a whole list, for example if the list consists of:
 
 ```
example.com
domains.com
target.com
```

If you do not add the `-i` option, the tool will make each target result in a single directory like:

```
example.com/

domains.com/

target.com/
```

But if you add the `-i` option, all the result will be saved in a single directory like:

`result/`

 
`-h` To display the help menu/options of the tool

# Output Example:

```

MP""""""`MM          dP       dP                                    dP                     
M  mmmmm..M          88       88                                    88                     
M.      `YM dP    dP 88d888b. 88d888b. 88d888b. dP    dP .d8888b. d8888P .d8888b. 88d888b. 
MMMMMMM.  M 88    88 88'  `88 88'  `88 88'  `88 88    88 Y8ooooo.   88   88ooood8 88'  `88 
M. .MMM'  M 88.  .88 88.  .88 88.  .88 88       88.  .88       88   88   88.  ... 88       
Mb.     .dM `88888P' 88Y8888' 88Y8888' dP       `88888P' `88888P'   dP   `88888P' dP       
MMMMMMMMMMM                                                                                
                                                                                           

		                Brust Down your domain
			  Author/Develop by: MrAashish0x1 Aka
			              Cybersploit*



[usage]:

-h ==> Help Menue
-t ==> Target Domain
-l ==> Domains List
-w ==> Wordlist
-d ==> Knockpy Deep Mode
-f ==> Knockpy Fast Mode
-g ==> Github Token
-i ==> Ignore Directory Splitting


[Explaination]:

[+] -h : It Show The Help Menue For You Such As: Syntax, Examples, Switches
[+] -t : To Use A Single Target Domain To Gather Subdomains On It { Put The Domain Without http Or https }
[+] -l : To Use A Multible Domains Listed In Text File {  Put Every Domain In A Single Line Without http Or https }
[+] -w : To Use A Wordlist For The Tools That Support Enumeration List Based { Optionally }
[+] -d : To Use Knockpy In Deep Mode | Switch Usage -> -d true or -d True
[+] -f : To Use Knockpy In Fast Mode | Switch Usage -> -f true or -f True
[+] -g : Set Github Token For Gathering Subdomains From Github { Optionally }
[+] -i : Ignore directory splitting for every domain in list { Only effective while using a list } | Switch usage -> -i true or -i True


[Exampels]:

=================================================
               Single Domains Based
=================================================

./subbruster -t domain.com -f true -g 55aa66bb4aa8mm9mmss334422-weqas -w /usr/share/wordlist/dirbuster/directories.jbrofuzz

./subbruster -t domains.com -d true -g 55aa66bb4aa8mm9mmss334422-weqas -w /usr/share/wordlist/dirbuster/directories.jbrofuzz


=================================================
               Domains List Based
=================================================

./subbruster -l domains.txt -d true -g 55aa66bb4aa8mm9mmss334422-weqas -w /usr/share/wordlist/dirbuster/directories.jbrofuzz -i

./subbruster -l domains.txt -f true -g 55aa66bb4aa8mm9mmss334422-weqas -w /usr/share/wordlist/dirbuster/directories.jbrofuzz



```
