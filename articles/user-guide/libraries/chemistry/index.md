---
title: Seznámení s knihovnou kvantové chemie
description: Seznamte se s knihovnou Microsoft Quantum pro chemii a jejím využitím při simulaci elektronických struktur na kvantových počítačích.
author: QuantumWriter
ms.author: ageller
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3fa606600db1641b9f8b86ccefebb7681f181b92
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847486"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Seznámení s knihovnou kvantové chemie

Simulace fyzických systémů hrála v oblasti kvantových výpočtů dlouhou dobu hlavní roli.  Důvodem je široce rozšířené přesvědčení, že kvantová dynamika je pro simulace na kvantových počítačích nevhodná, protože složitost simulace systému roste exponenciálně s velikostí zkoumaného kvantového systému.  Simulování problémů v chemii a nauce o materiálech zůstává pravděpodobně nejzajímavější oblastí použití kvantových výpočtů a umožnilo by nám testovat mechanismy chemických reakcí, které až dosud byly mimo naše schopnosti měření nebo simulace.  Pomohlo by nám také simulovat korelované elektronické materiály, jako jsou vysokoteplotní supravodiče. Seznam použití v této oblasti je nekonečný.

Účelem této dokumentace je poskytnout stručný úvod do problémů simulace elektronických struktur na kvantových počítačích, abychom čtenářům usnadnili pochopení role, jakou na tomto poli hraje řada aspektů knihovny hamiltoniánských simulací.  Začneme stručným úvodem do kvantové mechaniky a pak přejdeme ke způsobům, jak jsou v ní modelovány elektronické systémy.  Potom probereme možnosti, jak jde kvantovou dynamiku emulovat pomocí kvantového počítače.  Po dokončení probereme dvě metody používané ke kompilaci kvantové dynamiky do posloupností elementárních hradel: Trotter-Suzukiho dekompozice a qubitizace.
