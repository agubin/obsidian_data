![[Pasted image 20240303002324.png]]

Коммутатор L2 стандартно настраивается с пробросом через trunk интерфейс всех VLAN на роутер. Во VLAN4 расположен специально выделенный сервер для DHCP
его конфигурируем статично
![[Pasted image 20240303002505.png]]
Задаем на нем DHCP конфигурации для VLAN2 VLAN3
![[Pasted image 20240303002602.png]]
![[Pasted image 20240303002619.png]]
в конфигурациях посредством Start IP Address и Subnet Mask задается к какой сети он должен применяться. Т.е. когда запрос придет от сети 192.168.2.X - то задействуется DHCP c Start IP Address = 192.168.2.0. Так же выставляются DHCP опции
Но запрос от 192.168.2.X может прийти только через роутер, потому что у конечного устройства нет никакого IP. Поэтому при конфигурировании роутера нужно настроить перенаправление DHCP запросов

Настройка Router
```cisco
Router(config)#int fa0/0
Router(config-if)#no shutdown //поднимаем основной интерфейс

Router(config-if)#
%LINK-5-CHANGED: Interface FastEthernet0/0, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/0, changed state to up
Router(config-if)#exit

Router(config)#int fa0/0.2 //конфигурируем субинтерфейс для VLAN2
Router(config-subif)#
%LINK-5-CHANGED: Interface FastEthernet0/0.2, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/0.2, changed state to up
Router(config-subif)#encapsulation dot1Q 2 //привязываем VLAN2
Router(config-subif)#ip address 192.168.2.1 255.255.255.0 //задаем IP
Router(config-subif)#no shutdown //поднимаем субинтерфейс
Router(config-subif)#ip helper-address 192.168.4.2 //задаем перенаправление DHCP запросов
Router(config-subif)#exit

//Аналогично настраиваем остальные субинтерфейсы
Router(config)#int fa0/0.3
Router(config-subif)#
%LINK-5-CHANGED: Interface FastEthernet0/0.3, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/0.3, changed state to up
Router(config-subif)#encapsulation dot1Q 3
Router(config-subif)#ip address 192.168.3.1 255.255.255.0
Router(config-subif)#no shutdown 
Router(config-subif)#ip helper-address 192.168.4.2
Router(config-subif)#exit
Router(config)#int fa0/0.4
Router(config-subif)#
%LINK-5-CHANGED: Interface FastEthernet0/0.4, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/0.4, changed state to up
Router(config-subif)#encapsulation dot1Q 4
Router(config-subif)#ip address 192.168.4.1 255.255.255.0
Router(config-subif)#no shutdown 
Router(config-subif)#ip helper-address 192.168.4.2
Router(config-subif)#exit
Router(config)#exit
```

После этого включаем на конечных устройствах режим DHCP и они получают IP