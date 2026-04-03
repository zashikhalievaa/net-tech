---
title: "Презентация по лабораторной работе №2"
subtitle: "Сетевые технологии"
author: "Шихалиева Зурият Арсеновна"
date: "2025-09-22"
format:
  beamer:
    theme: metropolis
    aspectratio: 169
    pdf-engine: xelatex
    mainfont: DejaVu Sans
    lang: ru
    header-includes:
      - \usepackage{graphicx}
      - \graphicspath{{./image/}}
---

## Цель работы

Целью данной работы является изучение принципов технологий Ethernet и Fast Ethernet и практическое освоение методик оценки работоспособности сети, построенной на базе технологии Fast Ethernet.

---

## Задание

Требуется оценить работоспособность 100-мегабитной сети Fast Ethernet в соответствии с первой и второй моделями.

Конфигурации сети приведены на рис. 1.  
Топология сети представлена на рис. 2.

\begin{center}
\includegraphics[width=0.6\textwidth]{image/laba2_1.png}
\end{center}

\begin{center}
\includegraphics[width=0.5\textwidth]{image/laba2_2.png}
\end{center}

---

## Оценка работоспособности сети по первой модели

Диаметр домена коллизий вычисляется как сумма длин сегментов. Рассматриваются конфигурации, где все сегменты TX и присутствует два повторителя класса 2.

\textbf{Предельно допустимый диаметр = 205 м}

\begin{center}
\includegraphics[width=0.7\textwidth]{image/laba2_3.png}
\end{center}

---

## Результаты по первой модели

По первой модели работоспособными являются сети \textbf{1, 3 и 4}.

\begin{center}
\includegraphics[width=0.6\textwidth]{image/laba2_4.png}
\end{center}

---

## Оценка работоспособности сети по второй модели

В нашей конфигурации все сегменты 100BASE-TX и используется витая пара категории 5.

| Компонент пути | Время, би |
|----------------|----------|
| Пара терминалов TX | 100 |
| Сегмент 100 м | 111,2 |
| Повторитель класса II | 92 |

\begin{center}
\includegraphics[width=0.5\textwidth]{image/laba2_5.png}
\end{center}

---

## Результаты по второй модели

Сеть работоспособна, если PDV ≤ 512 би.

По второй модели работоспособны сети \textbf{1, 3 и 4}.

\begin{center}
\includegraphics[width=0.6\textwidth]{image/laba2_6.png}
\end{center}

---

## Выводы

В ходе выполнения лабораторной работы №2:
- Изучили принципы Ethernet и Fast Ethernet
- Освоили методики оценки работоспособности сети
- Определили работоспособные конфигурации
