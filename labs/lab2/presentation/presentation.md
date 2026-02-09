---
lang: ru-RU
title: Анализ трафика в Wireshark
subtitle: Лабораторная работа №3
author:
  - Чилеше Лупупа
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 13 декабря 2025
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

Изучение кадров Ethernet и анализ PDU протоколов канального, транспортного  
и прикладного уровней стека TCP/IP с использованием анализатора Wireshark.

# Выполнение работы

## Получение параметров сетевого соединения

![Результат выполнения команды ipconfig](Screenshot_1.png){ width=70% }

## Захват ICMP-трафика

![Проверка доступности шлюза](Screenshot_2.png){ width=70% }

## ICMP Echo Request / Reply

![ICMP Echo Request](Screenshot_3.png){ width=70% }

## ICMP Echo Request / Reply

![ICMP Echo Reply](Screenshot_4.png){ width=70% }

## Анализ ARP-кадров

![ARP-запрос](Screenshot_5.png){ width=70% }

## ICMP при обращении к доменному имени

![Ping доменного имени](Screenshot_6.png){ width=70% }

## HTTP-трафик

![HTTP-трафик](Screenshot_10.png){ width=70% }

## DNS-трафик

![DNS-запрос](Screenshot_11.png){ width=70% }

## QUIC-трафик

![QUIC Initial-пакет](Screenshot_12.png){ width=70% }

## Установка TCP-соединения

![TCP handshake](Screenshot_13.png){ width=70% }

## График потока TCP

![График потока TCP](Screenshot_14.png){ width=70% }

# Вывод

## Вывод

- Изучены принципы MAC- и IP-адресации
- Выполнен захват и анализ сетевого трафика
- Исследованы протоколы:
  - ARP, ICMP
  - TCP, UDP, QUIC
  - HTTP и DNS
- Практически подтверждена работа TCP handshake и механизмов надёжной передачи данных
