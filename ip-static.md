# Ip Static Config

- you can get the ip static from you isp
- the static ip should be set on your router (modem)
	- if you have sim card static ip you should first 
	  activate it in a phone then insert into your modem
- you can see the static ip is set on your modem admin panel
- the address of admin panel usually is the first ip in your
  lan range for example `192.168.1.1`, `192.168.10.1`, ...
- then you should map your service from lan to wan with one
  of following ways 
- 3 ways to config ip static wan/lan mapping
	- dmz (host mapping)
	- specific application (app mapping)
	- port mapping

> ***THE SSH PORT (`22`) IS USUALLY BLOCKED BY THE ISPs, 
> SO DON'T USE FROM IT IN WAN PORT***
