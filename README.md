<p align="center" dir="auto"><strong>Commands nmap and others</strong></p>  
  
<div>
  <p align="center" dir="auto">
  <a href="https://www.instagram.com/prohacker77_/" target="_blank"><img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=39ff14&logoColor=white&color=black" target="_blank"></a>
  <a href="https://discord.gg/Z2C2CyVZFU" target="_blank"><img src="https://img.shields.io/badge/-Discord-7289DA?style=for-the-badge&logo=discord&logoColor=39ff14&logoColor=white&color=black" target="_blank"></a>
  <a href="https://www.linkedin.com/in/caique-barreto-7809b2217/" target="_blank"><img src="https://img.shields.io/badge/-LinkdIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=39ff14&logoColor=white&color=black" target="_blank"></a>
  <a href="mailto:caique.hbarreto@gmail.com" target="_blank"><img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=39ff14&logoColor=white&color=black" target="_blank"></a>
  <a href="https://t.me/PeakyBlindersW" target="_blank"><img src="https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=39ff14&logoColor=white&color=black" target="_blank"></a>
  </p>
</div>

### `Basic and efective scan`

```shell

nmap -sS -sCV -Pn <target> -oN nmap.txt

```

### `SSH Brute Force credentials`
```shell

nmap -p 22 --script ssh-brute --script-args userdb=username.txt,passdb=password.txt <target> -oN nmap.txt

```

### `TFTP enum`
```shell

nmap -sU -p 69 --script tftp-enum.nse --script-args tftp-enum.filelist=customlist.txt <host> -oN nmap.txt

```

### `MySql enum`
```shell
nmap --script=mysql-enum -p 3306 <target> -oN nmap.txt
```

### `Smtp enum | brute`
```shell

nmap --script smtp-enum-users.nse [--script-args smtp-enum-users.methods={EXPN,VRFY,RCPT},...] -p 25,465,587 <host> -oN nmap.txt
nmap --script=smtp-enum-users --script-args smtp.domain=value,smtp-enum-users.methods=value <target> -oN nmap.txt
nmap -p 25 --script smtp-brute <target> -oN nmap.txt

```

### `SNMP`
```shell

nmap -sV <target> -p 161

```

### `jabber xmpp`
```shell

nmap -sV <target> -p5222,5269

```

## Command Enum4linux

### `Enum SMB`
```shell

enum4linux <target> -A -d

```
