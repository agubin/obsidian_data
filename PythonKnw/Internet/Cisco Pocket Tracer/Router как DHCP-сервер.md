![[Pasted image 20240302233919.png]]

В этой схеме все конечные устройства находятся в одном сегменте - дефолтном VLAN
==Поэтому коммутатор L2 не настраиваться вообще==

На роутере производятся следующие настройки
```cisco
Router(config)#int fa0/0
Router(config-if)#no shutdown //поднимаем интерфейс приема

Router(config-if)#
%LINK-5-CHANGED: Interface FastEthernet0/0, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/0, changed state to up

Router(config-if)#ip address 192.168.1.1 255.255.255.0 //задаем IP-address
Router(config-if)#exit
Router(config)#ip dhcp pool DHCP //конфигурируем pool адресов
Router(dhcp-config)#network 192.168.1.0 255.255.255.0 //задаем сеть в которой будут раздаваться адреса. Сеть должна включать в себя IP-address интерфейса по которому осуществляется прием
Router(dhcp-config)#default-router 192.168.1.1 //задаем дефолтный маршурт/гейтвей
Router(dhcp-config)#dns-server 8.8.8.8 //задаем dns-server
Router(dhcp-config)#exit
Router(config)#ip dhcp excluded-address 192.168.1.1 255.255.255.0 //исключаем из раздачи IP-address интерфейса по которому осуществялется прием
Router(config)#ip dhcp excluded-address 192.168.1.100 255.255.255.0 // и оставляем IP для какого-нибудь сервера
```

Дальше просто включаем на конечных устройствах DHCP режим и они получают адреса сами