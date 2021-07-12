# frp
frp for `win10`


# frp for win10 client

frp on `win10` system auto open with operation system. 

# step 1:

you need dowload winsw tools ,url address: 
``` 
https://github-releases.githubusercontent.com/500093/8ade6780-878a-11eb-89b9-6403efa62dac?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20210609%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20210609T023903Z&X-Amz-Expires=300&X-Amz-Signature=c55dc651bd4678ec4c0e22450022d26be59f63372555d34cc46770988cf3d990&X-Amz-SignedHeaders=host&actor_id=0&key_id=0&repo_id=500093&response-content-disposition=attachment%3B%20filename%3DWinSW-x64.exe&response-content-type=application%2Foctet-stream
```

# step 2 :
ref: https://blog.csdn.net/hubz131/article/details/97180597  this document tells you how to make the exe file to windows service.

[frp_0.37.0_windows_amd64.zip](https://github.com/glodenfish/frp/raw/main/frp_0.37.0_windows_amd64.zip)

```rar
example for frp on windows plateform . add frpc.exe to windows service

```

[frp_0.37.0_windows_amd64_win10_service.rar](https://github.com/glodenfish/frp/blob/main/frp_0.37.0_windows_amd64_win10_service.rar)
# step 3 :
make configuration for your frp client. as follows:

## 3.1 frpc.ini

```ini
 [common]
 server_addr = xxx.xxx.xxx.xxx  # server addr allows ip address or domain name
 server_port = 7000  # server port  any ports . if you are use clouds  needs open privileges for your ports. pay attention to firewalld. 
 token = lxy2021  # token is clear. the same as the server address. 

 #topic is everything you like.
 [wms-web]  
 type = http   # type of your application such as http https tcp upd etc.
 local_ip = 192.168.83.100  #local ip  or  LAN ip
 local_port = 80   # local port
 remote_port = 8080   # frps server port for communication between client and server.
 custom_domains = xxx.xxx.xxx.xxx  # consistence with frps server

 #[web2_xxxxx]
 #type = https
 #local_ip = 192.168.1.2
 #local_port = 5001
 #custom_domains = xxx.xxx.xxx.xxx

 #[tcp1_xxxxx]
 #type = tcp
 #local_ip = 192.168.1.2
 #local_port = 22
 #remote_port = 22222
 
```




