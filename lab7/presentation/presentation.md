---
lang: ru-RU
title: Сетевые технологии
subtitle: Настройка DHCP, DHCPv6, SLAAC и IPv6 в GNS3
author:
  - Шихалиева Зурият Арсеновна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 29 ноября 2025
toc: false
slide_level: 2
aspectratio: 169
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Цель работы

## Основная цель

Получить навыки настройки DHCP, DHCPv6 Stateless и Stateful, SLAAC и IPv6-адресации в виртуальной среде GNS3.

# Выполнение работы 

## Топология IPv4

![Топология](image/1.png){ width=80% }

## Настройка VyOS

- Смена имени хоста и доменного имени  
- Создание нового пользователя  
- Назначение адреса 10.0.0.1/24  
- Настройка DHCP-сервера

![Консоль](image/2.png){ width=70% }

## DHCP-сервер

- Подсеть: **10.0.0.0/24**  
- Диапазон: **10.0.0.2–10.0.0.253**  
- DNS: **10.0.0.1**  
- Домен: **trseidaliev.net**

![DHCP range](image/3.png){ width=75% }

## Клиент PC1

IP: 10.0.0.2/24  
Gateway: 10.0.0.1  
DNS: 10.0.0.1

![PC1 DHCP](image/4.png){ width=75% }

## Проверка работы DHCP

![PC1 show ip](image/5.png){ width=70% }

## Последовательность обмена

- Discover  
- Offer  
- Request  
- ACK

![DHCP Wireshark](image/8.png){ width=100% }

## Новая расширенная топология

![Топология IPv6](image/9.png){ width=80% }

## Настройка адресов IPv6

- eth1 → 2000::1/64  
- eth2 → 2001::1/64  

![Interfaces IPv6](image/10.png){ width=70% }

## Router Advertisement (RA)

- Префикс 2000::/64  
- other-config-flag: получение DNS через DHCPv6

![RA настройка](image/11.png){ width=80% }

## DHCPv6 Stateless

Параметры выдаются:  
- DNS: 2000::1  
- Domain-search: trseidaliev.net

![DHCPv6 Stateless конфигурация](image/12.png){ width=75% }

## Клиент PC2 (SLAAC)

Адрес: SLAAC (2000::/64)  
Маршруты добавлены автоматически

![PC2 IPv6 SLAAC](image/13.png){ width=80% }

## DHCPv6 Stateless: получение DNS

![PC2 dhclient -6](image/14.png){ width=80% }

## Анализ DHCPv6 Stateless

![DHCPv6 Stateless Wireshark](image/16.png){ width=100% }

## Включение режима Stateful

- RA: managed-flag  
- Диапазон адресов: **2001::100 – 2001::199**  
- DNS: 2001::1  
- Domain-search: trseidaliev.net

![Stateful настройки](image/17.png){ width=80% }

## PC3 — до получения адреса

![PC3 SLAAC](image/18.png){ width=75% }

## PC3 — получение адреса DHCPv6 Stateful

![dhclient Stateful](image/19.png){ width=80% }

## PC3 — после получения адреса

Полная конфигурация:  
- IPv6: 2001::198 или 2001::199  
- DNS: 2001::1  
- Пинг до 2001::1 успешен

![PC3 IPv6 полный](image/20.png){ width=80% }

## Просмотр аренд DHCPv6 Stateful

![Stateful leases](image/21.png){ width=75% }

## Пакеты Solicit, Advertise, Request, Reply

![Wireshark DHCPv6 Stateful](image/22.png){ width=100% }

# Итоги

## Основные достижения

- Настроен DHCP для IPv4  
- Настроены SLAAC, DHCPv6 Stateless и Stateful  
- Выполнена полная проверка маршрутизации и связности  
- Проанализирован сетевой трафик всех DHCP-механизмов  
- Подтверждена корректная работа всех служб распределения адресов
