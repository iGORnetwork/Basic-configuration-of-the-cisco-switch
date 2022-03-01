
# ДЗ (1)  Команды IOS. Базовая конфигурация устройств 

## Часть 1. Проверка конфигурации коммутатора по умолчанию
1 Switch ➝ enable ➝ show running-config 

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_1.png)
![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_2.png)
# Часть 2. Создание сети и настройка основных параметров устройства
## Настройка базовых параметров коммутатора.
1. Установка пароля :

a) Switch ➝ enable ➝ configure terminal ➝ line console 0 ➝ logging synchronous 

b) Switch ➝ enable ➝ configure terminal ➝ line console 0 ➝ password cisco ➝ login

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_3.png)

c) Switch ➝ enable ➝ configure terminal ➝ enable secret class

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_6.png)

d) скрываем пароли  S1(config)#service password-encryption


2. Отключения поиска списка доменных имен :

a) Switch ➝ enable ➝ configure terminal ➝ no ip domain lookup


3. Изменения имени устройство :

a) Switch ➝ enable ➝ configure terminal ➝ hostname S1

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_4.png)

4) Настройка даты и вермяни 
a) Switch ➝ enable ➝ clock set h:min:sec den mes god
![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_5.png)

5. Настройка терминальных линий для удалённого подключения 

a) S1 ➝ enable ➝ configure terminal ➝ line VTY 0 4 ➝ password cisco ➝ login

b) S1 ➝ enable ➝ configure terminal ➝ transport input all

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_7.png)

6. Настройка Ip адреса 

a) S1 (config) ➝ #interface vlan 1

b) S1 (config-if) ➝ #ip address 192.168.1.2 255.255.255.0

c) S1 (config-if) ➝ #no shutdown

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_8.png)

7. Сохраняем настройки 

a) S1# ➝ #copy running-config startup-config

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_9.png)

# Настройка PC-A
1. Установим IP

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_10.png)

2. Проверим соединение 
 
PC-A ➝ CMD ➝ ping 192.168.1.2

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_11.png)
 
3. Подключаемся к коммутатору по TELNET

а) PC-A ➝ CMD ➝ Telenet open 192.168.1.2

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_12.png)
![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_13.png)

# ДЗ (2) Канальный уровень. Ethernet 
 1. Проводим базовые настройки switch end PC согласно таблице 

Устройство	                      Интерфейс	                   IP-адрес	                      Маска 

S1	                              VLAN 1	                      192.168.1.1	                   255.255.255.0

S2	                              VLAN 1	                      192.168.1.2	                   255.255.255.0

PC-A	                            NIC	                         192.168.1.11	                  255.255.255.0

PC-B	                            NIC	                         192.168.1.12	                  255.255.255.0

# S1
![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_14.png)

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_15.png)

# S2
![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_16.png)

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_17.png)

# PC-A
![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_18.png)

# PC-B
![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_19.png)

2. Просмотрите таблицу МАС-адресов коммутатора S2

S2# ➝ show mac address-table

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_20.png)

3. Очистка таблицы МАС-адресов коммутатора S2 и снова отобразить таблицу МАС-адресов.

S2# clear mac address-table dynamic 

S2# show mac address-table 

После отчистки отображается один mac address 
Если отправить эхо-запрос с PC-B ping 192. 168. 1. 1 192. 168. 1. 2 192. 168. 1. 11 тогда в таблице появляется 3 mac адреса  с которых выполняли команду ping

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_21.png)

3. Просмотр работы протокола ARP

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_22.png)
![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_23.png)
