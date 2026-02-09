---
lang: ru-RU
title: Адресация IPv4 и IPv6. Настройка DHCP
subtitle: Лабораторная работа №7
author:
  - Чилеше Лупупа
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 16 декабря 2025
toc: false
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Цели и задачи работы

## Цель лабораторной работы

Получение навыков настройки службы DHCP на сетевом оборудовании для распределения адресов IPv4 и IPv6.

# DHCP для IPv4 (VyOS + VPCS)

## Топология и захват трафика

![Топология сети IPv4 (VyOS, коммутатор, VPCS)](01.png){ width=75% }

## Первичная настройка VyOS

![Изменение host-name, domain-name, создание пользователя](02.png){ width=75% }

## Настройка IPv4 и DHCP-сервера

![IP 10.0.0.1/24 на eth0 и DHCP-пул 10.0.0.2–10.0.0.253](03.png){ width=75% }

## Получение IPv4 по DHCP на клиенте

![DHCP-обмен на PC1 и получение параметров сети](04.png){ width=75% }

## Проверка параметров и связности

![show ip и ping 10.0.0.1](05.png){ width=75% }

## Статистика DHCP и выданные адреса

![show dhcp server statistics и show dhcp server leases](06.png){ width=75% }

## Журнал работы DHCP-сервера

![События DHCPDISCOVER/DHCPOFFER/DHCPREQUEST/DHCPACK](07.png){ width=75% }

## Анализ DHCP-трафика

![Пакеты DHCP Discover/Offer/Request/ACK в анализаторе](08.png){ width=75% }

# DHCPv6 Stateless

## Расширенная топология

![Топология для IPv6 (добавлены sw-02, sw-03 и клиенты Kali Linux)](09.png){ width=75% }

## IPv6-адресация на VyOS

![eth1: 2000::1/64, eth2: 2001::1/64](10.png){ width=75% }

## Настройка RA и DHCPv6 Stateless

![RA на eth1 (other-config-flag) и DHCPv6 common-options](11.png){ width=75% }

## Проверка конфигурации VyOS

![Просмотр конфигурации DHCPv6 и Router Advertisement](12.png){ width=75% }

## Проверка адресации на PC2 (SLAAC)

![IPv6-адрес из префикса 2000::/64 и маршрут по умолчанию](13.png){ width=75% }

## Запрос параметров по DHCPv6

![Получение DNS и domain-search (без назначения адреса)](14.png){ width=75% }

## Контроль на стороне сервера

![В Stateless аренды адресов отсутствуют](15.png){ width=75% }

# DHCPv6 Stateful

## Настройка DHCPv6 Stateful на VyOS

![Пул адресов 2001::100–2001::199, DNS 2001::1, domain-search](16.png){ width=75% }

## Проверка PC3 до выдачи адреса

![Начальные параметры сети и маршруты IPv6](17.png){ width=75% }

## Получение IPv6-адреса по DHCPv6

![dhclient -6 -v: адрес получен, зафиксировано время аренды](18.png){ width=75% }

## Проверка связности и DNS на PC3

![ping 2001::1 и параметры resolv.conf](19.png){ width=75% }

## Выданные аренды DHCPv6 на маршрутизаторе

![run show dhcpv6 server leases: активная аренда](20.png){ width=75% }

# Вывод

## Вывод

- Выполнена настройка DHCP для IPv4 на VyOS, подтверждена автоматическая выдача адреса и параметров сети клиенту.
- Реализованы два режима DHCPv6:
  - Stateless: IPv6-адрес формируется SLAAC, DHCPv6 передаёт дополнительные параметры (DNS, domain-search).
  - Stateful: IPv6-адрес назначается DHCPv6-сервером из заданного пула.
- Анализ захваченного трафика подтвердил корректную последовательность сообщений DHCP/DHCPv6 и работу Router Advertisements.
