---
title: Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK)
description: Jak nainstalovat sadu Microsoft Quantum Development Kit pro C#, Python a prostředí Jupyter Notebook
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680193"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalace sady Microsoft Quantum Development Kit (QDK)

Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK), abyste mohli začít s kvantovým programováním. Sada QDK obsahuje tyto komponenty:

- Programovací jazyk Q#
- Sada knihoven s abstraktními komplexními funkcemi v jazyku Q#
- Rozhraní API pro jazyky Python a .NET (C#, F# a VB.NET) pro spouštění kvantových programů napsaných v Q#
- Nástroje pro usnadnění vývoje

Programy v Q# jsou často spárovány s hostitelským programem napsaným v jazyce .NET (obvykle C#) nebo Pythonu. Díky tomu můžeme volat kvantové operace v rámci klasického programu.
Kromě toho sada QDK poskytuje podporu Q# pro poznámkové bloky Jupyter s jádrem IQ# Jupyter.

Sada QDK je k dispozici pro víc vývojových prostředí. Z následujících částí vyberte upřednostňovanou instalaci:

- [Aplikace příkazového řádku v Q#:](xref:microsoft.quantum.install.standalone) Tento přístup zvolte, když chcete pracovat s jazykem Q# z příkazového řádku. Tato možnost nevyžaduje ovladač ani hostitelský program jako následující možnosti.
- [Instalace Q # pro poznámkové bloky Jupyter:](xref:microsoft.quantum.install.jupyter) Toto prostředí vyberte, pokud chcete spouštět kód Q# v buňkách s vloženým textem nebo vytvořit interaktivní kurzy kvantových výpočtů. 
- [Vývoj s využitím Q# a Pythonu:](xref:microsoft.quantum.install.python) Toto prostředí vyberte, pokud chcete kombinací jazyků Python a Q# vytvořit hostitelský program v Pythonu, který volá operace v Q#.
- [Vývoj s využitím Q# a C# nebo F#:](xref:microsoft.quantum.install.cs) Toto prostředí vyberte, pokud chcete kombinací jazyků C# nebo F# a Q# vytvořit hostitelský program v .NET, který volá operace v Q#.
