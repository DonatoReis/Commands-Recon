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
### `Only Open Ports and Banner Grab`

```shell
nmap -n -Pn -sS <target> --open -sV
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

## TCP Connect Scan ( -sT)
```shell
A varredura de conex??o usa a chamada do sistema com o mesmo nome para varrer as m??quinas, em vez de depender de pacotes brutos como a maioria dos outros m??todos. Geralmente ?? usado por usu??rios Unix sem privil??gios e contra alvos IPv6 porque a varredura SYN n??o funciona nesses casos.
```

## UDP Scan ( -sU)
```shell
N??o se esque??a das portas UDP ??? elas tamb??m oferecem muitas brechas de seguran??a.
```

## TCP FIN, NULL e Xmas Scans ( -sF, -sX, -sN)
```shell
Esses tipos de varredura de prop??sito especial s??o adeptos de passar por firewalls para explorar os sistemas por tr??s deles. Infelizmente, eles dependem do comportamento de destino que alguns sistemas (particularmente variantes do Windows) n??o exibem.
```

## TCP ACK Scan ( -sA)
```shell
A varredura ACK ?? comumente usada para mapear conjuntos de regras de firewall. Em particular, ajuda a entender se as regras de firewall s??o stateful ou n??o. A desvantagem ?? que n??o consegue distinguir portas abertas de portas fechadas.
```

## TCP Window Scan ( -sW)
```shell
A varredura de janela ?? como a varredura de ACK, exceto que ?? capaz de detectar portas abertas versus portas fechadas em determinadas m??quinas.
```

## TCP Maimon Scan ( -sM)
```shell
Esse tipo obscuro de varredura de evas??o de firewall ?? semelhante a uma varredura FIN, mas tamb??m inclui o sinalizador ACK. Isso permite que ele obtenha mais firewalls de filtragem de pacotes, com a desvantagem de funcionar contra ainda menos sistemas do que a varredura FIN.
```

## TCP Idle Scan ( -sI zombie host) 
```shell
A varredura ociosa ?? o tipo de varredura mais furtivo de todos e, ??s vezes, pode explorar relacionamentos de endere??os IP confi??veis. Infelizmente, tamb??m ?? lento e complexo.
```

## Varredura de Protocolo IP ( -sO)
```shell
A varredura de protocolo determina quais protocolos IP (TCP, ICMP, IGMP, etc.) s??o suportados pela m??quina de destino. Isso n??o ?? tecnicamente uma varredura de porta, pois percorre os n??meros de protocolo IP em vez de n??meros de porta TCP ou UDP. No entanto, ele ainda usa a -pop????o de selecionar n??meros de protocolo verificados, relata seus resultados com o formato normal da tabela de portas e at?? usa o mesmo mecanismo de verifica????o subjacente que os m??todos de verifica????o de portas reais. Portanto, est?? perto o suficiente de uma varredura de porta que pertence aqui.
```

## TCP FTP Bounce Scan ( -b)
```shell
Esse tipo de varredura obsoleto engana os servidores FTP para que executem varreduras de porta por proxy. A maioria dos servidores FTP agora s??o corrigidos para evitar isso, mas ?? uma boa maneira de passar por firewalls restritivos quando funciona.
```
