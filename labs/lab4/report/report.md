---
## Front matter
title: "Отчёт по лабораторной работе 4"
subtitle: "Подготовка экспериментального стенда GNS3"
author: "Чилеше Лупупа"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Установка и настройка GNS3 и сопутствующего программного обеспечения.


# Выполнение работы

## Установка и проверка корректности запуска GNS3 VM

В рамках выполнения задания была установлена система моделирования компьютерных сетей **GNS3** совместно с виртуальной машиной **GNS3 VM**. После развертывания виртуальной машины был выполнен её первичный запуск и проверка состояния сервера.

На экране отображается информация о версии GNS3 server, используемой операционной системе, параметрах виртуализации, а также сетевых настройках и способах подключения к серверу:

![Информация о состоянии и параметрах GNS3 VM](Screenshot_1.png){ #fig:001 width=80% }

## Подключение клиента GNS3 к удалённому серверу

После успешного запуска виртуальной машины выполнена настройка подключения клиента GNS3 к удалённому контроллеру. В мастере настройки указаны протокол подключения, IP-адрес сервера, порт, а также учётные данные администратора.

![Настройка подключения к удалённому GNS3 контроллеру](Screenshot_2.png){ #fig:002 width=80% }

Корректность подключения подтверждена успешным переходом к следующим этапам настройки среды.

## Импорт образа маршрутизатора FRR

Для выполнения лабораторной работы в систему был импортирован образ маршрутизатора **FRR (Free Range Routing)**. В окне выбора шаблонов выполнен поиск соответствующего устройства и выбран официальный шаблон проекта FRRouting.

![Выбор шаблона маршрутизатора FRR](Screenshot_3.png){ #fig:003 width=80% }

В процессе установки был выбран доступный образ версии FRR, найденный локально, готовый к установке в среду GNS3.

![Выбор версии и файлов образа FRR](Screenshot_4.png){ #fig:004 width=80% }

После добавления устройства в проект выполнен запуск маршрутизатора. На консоли отображается процесс загрузки операционной системы Alpine Linux и запуск сервисов FRRouting, что подтверждает корректность импорта и работоспособность образа.

![Запуск и загрузка маршрутизатора FRR](Screenshot_5.png){ #fig:005 width=80% }

## Импорт образа маршрутизатора VyOS

Аналогичным образом в систему был импортирован образ маршрутизатора **VyOS**. В мастере установки выбран шаблон VyOS и указан локально доступный образ версии 1.3.3, готовый к использованию.

![Выбор версии и файлов образа VyOS](Screenshot_6.png){ #fig:006 width=80% }

После добавления маршрутизатора в проект выполнен его запуск. В консольном окне отображается процесс загрузки системы VyOS, обнаружение виртуальной среды и инициализация сетевых компонентов.

![Загрузка и запуск маршрутизатора VyOS](Screenshot_7.png){ #fig:007 width=80% }

# Вывод

В ходе выполнения работы была успешно установлена и настроена среда моделирования компьютерных сетей GNS3 с использованием виртуальной машины GNS3 VM. Выполнено подключение клиента к удалённому серверу, а также корректно импортированы и запущены образы маршрутизаторов FRR и VyOS. Работоспособность всех компонентов подтверждена, лабораторный стенд полностью готов к дальнейшему использованию.
