---
title: Seznámení s balíčkem kvantové chemie | Microsoft Docs
description: Seznámení s balíčkem kvantové chemie
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
ms.openlocfilehash: e5a9dd70874f1ae0baf4b781346278195a980a7e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960424"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Seznámení s knihovnou kvantové chemie

Simulace fyzických systémů hrála v oblasti kvantových výpočtů dlouhou dobu hlavní roli.  Důvodem je široce rozšířené přesvědčení, že kvantová dynamika je pro simulace na kvantových počítačích nevhodná, protože složitost simulace systému roste exponenciálně s velikostí zkoumaného kvantového systému.  Simulování problémů v chemii a nauce o materiálech zůstává pravděpodobně nejzajímavější oblastí použití kvantových výpočtů a umožnilo by nám testovat mechanismy chemických reakcí, které až dosud byly mimo naše schopnosti měření nebo simulace.  Pomohlo by nám také simulovat korelované elektronické materiály, jako jsou vysokoteplotní supravodiče. Seznam použití v této oblasti je nekonečný.

Účelem této dokumentace je poskytnout stručný úvod do problémů simulace elektronických struktur na kvantových počítačích, abychom čtenářům usnadnili pochopení role, jakou na tomto poli hraje řada aspektů knihovny hamiltoniánských simulací.  Začneme stručným úvodem do kvantové mechaniky a pak přejdeme ke způsobům, jak jsou v ní modelovány elektronické systémy.  Potom probereme možnosti, jak jde kvantovou dynamiku emulovat pomocí kvantového počítače.  Po dokončení probereme dvě metody používané ke kompilaci kvantové dynamiky do posloupností elementárních hradel: Trotter-Suzukiho dekompozice a qubitizace.
