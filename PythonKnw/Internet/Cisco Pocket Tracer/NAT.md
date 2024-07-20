![[Pasted image 20240303192859.png]]

Конечные устройства в VLAN2 настроены статично, с дефолтным шлюзом на Router0. Сервер во VLAN3 настроен статично, с дефолтным шлюзом на Router0. Switch0 настроен стандартно на проброс VLAN2, VLAN3 до Router0 по trunk. 

Router0 принимает VLAN2, VLAN3 по енкапсулированным суб-интерфейсам. На нем задан дефолтный маршрут на Router1.

Router1 сконфигурирован просто поднятием 2 интерфейсов присоединения.

Server1 сконфигурирован статично с дефолтным шлюзом на Router1.

Server1 и Router0 могут пинговать друг друга.

Для того что бы Server1 и устройства в сетях за Router0 у которых серые IP адреса могли общаться, нужно настроить NAT на Router0.

```cisco
//Сначала нужно определить внешние и внутренние интерфейсы NAT 
Router(config)#int fa0/1 //интерфейс который смотрит в Internet - это внешний
Router(config-if)#ip nat outside
Router(config-if)#exit
//Интерфейсы по которым проброшены VLAN внутренней сети - это внутреннии
Router(config)#int fa0/0.2
Router(config-subif)#ip nat inside
Router(config-subif)#exit
Router(config)#int fa0/0.3
Router(config-subif)#ip nat inside
Router(config-subif)#exit
//Нужно создать access лист, в котором указано в отношении каких внутренних сетей нужно применять NAT
Router(config)#ip access-list standard FOR-NAT
Router(config-std-nacl)#permit 192.168.2.0 0.0.0.255 //VLAN2
Router(config-std-nacl)#permit 192.168.3.0 0.0.0.255 //VLAN3
Router(config-std-nacl)#exit
//здесь указано что натить надо со стороны inside с использованием access-list FOR-NAT с указаннием интерфейса со стороны которого приходят запросы, использую перегруженный NAT(overload)
Router(config)#ip nat inside source list FOR-NAT interface fa0/1 overload
```

После с машины с IP 192.168.2.2 выполним пинг на внешний сервер c IP 192.168.20.2, дождемся 2 пакетов. И на роутере Router0 можно посмотреть

```cisco
Router#show ip nat translations 
Pro  Inside global     Inside local       Outside local      Outside global
icmp 192.168.10.2:3    192.168.2.2:3      192.168.20.2:3     192.168.20.2:3
icmp 192.168.10.2:4    192.168.2.2:4      192.168.20.2:4     192.168.20.2:4
```
Видно что в Inside пинг из сети 192.168.2.2 транслируется в адрес 192.168.10.2

Далее настроим доступ из внешней сети к Server0 в VLAN2. Для этого используем static NAT. Для этого нужно сконфигурировать Router0
```cisco
//Здесь указывается что натить надо запросы приходящие на порт 80 внешней сети и отправлять их на сервер тоже порт 80(HTTP)
Router(config)#ip nat inside source static tcp 192.168.3.2 80 192.168.10.2 80
```
Сконфигурируем HTTP ответ на Server0
![[Pasted image 20240303201248.png]]


Если на Server1 вызовем порт 80 на Router0 то получим НTTP ответ от Server0
![[Pasted image 20240303201155.png]]
