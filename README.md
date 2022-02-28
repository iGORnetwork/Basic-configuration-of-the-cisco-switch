# Basic-configuration-of-the-cisco-switch
## Часть 1. Проверка конфигурации коммутатора по умолчанию
1 Switch ➝ enable ➝ show running-config 

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_1.png)
![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_2.png)
# Часть 2. Создание сети и настройка основных параметров устройства
## Настройка базовых параметров коммутатора.
1. Установка пароля :

a) Switch ➝ enable ➝ configure terminal ➝ line console 0 ➝ logging synchronous 

b) Switch ➝ enable ➝ configure terminal ➝ line console 0 ➝ password cisco ➝ login

c) Switch ➝ enable ➝ configure terminal ➝ enable secret class

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_3.png)

2. Отключения поиска списка доменных имен :

a) Switch ➝ enable ➝ configure terminal ➝ no ip domain lookup


3. Изменения имени устройство :

a) Switch ➝ enable ➝ configure terminal ➝ hostname S1

![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_4.png)

4) Настройка даты и вермяни 
a) Switch ➝ enable ➝ clock set h:min:sec den mes god
![](https://github.com/iGORnetwork/Basic-configuration-of-the-cisco-switch/blob/main/image/Screenshot_5.png)
