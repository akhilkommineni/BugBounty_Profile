# BugBounty_Profile

This project is to help create easy aliases to run via an SSH/terminal. If you see anything missing, feel free to add them.


**Broken Link Checker** *Date* `14/05/2020`
~ bug bounty Profile for Broken Link Checker ~

Tool :- waybackurls,burl @TomNomNom

```bash
 ▶  nano ~/.bash_profile
```

```bash
blc() {
subfinder -d $1 | httprobe | waybackurls | egrep -iv ".(jpg|gif|css|png|woff|pdf|svg|js)" | burl | tee brokenlink.txt
}
```
```bash
▶ source ~/.bash_profile
```
```
▶ blc lol.com

```



 
**Paramlist** *Date* `01/05/2020`

Recon_profile for create your own param wordlist @1ndianl33t

Tool waybackurls,unfur @TomNomNom

```bash
 ▶  nano ~/.bash_profile
```

```bash
paramlist() { waybackurls $1 | grep "?" | unfurl -u keys | tee -a paramlist.txt
}

```
```bash


▶ Source ~/.bash_profile

```
```bash


▶ paramlist lol.com

```



**Subdomain Takeover**  *Date* `29/04/2020`





```bash
subtakeover() {
subfinder -d $1 >> hosts | assetfinder -subs-only $1 >> hosts | amass enum -norecursive -noalts -d $1 >> hosts | subjack -w hosts -t 100 -timeout 30 -ssl -c ~/subjack/fingerprints.json -v 3 >> takeover 
}
```































