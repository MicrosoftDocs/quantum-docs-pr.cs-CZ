---
title: Instalace sady Microsoft Quantum Development Kit (QDK)
description: Postup instalace sady Microsoft Quantum Development Kit pro různá prostředí
author: natke
ms.author: nakersha
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 2041b90ba021b7640615d73c35841cc21f025ac0
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426459"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalace sady Microsoft Quantum Development Kit (QDK)

Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK), abyste mohli začít s kvantovým programováním. Sada QDK obsahuje tyto komponenty:

- Programovací jazyk Q#
- Sada knihoven, které abstrahují komplexní funkce v Q#
- Rozhraní API pro jazyky Python a .NET (C#, F# a VB.NET) pro spouštění kvantových programů napsaných v Q#
- Nástroje pro usnadnění vývoje

Programy v Q# je možné spustit jako samostatné aplikace s využitím Visual Studio Code nebo sady Visual Studio nebo prostřednictvím poznámkových bloků Jupyter s jádrem IQ# Jupyter.

Také je možné je spárovat s hostitelským programem v jazyce .NET (obvykle v jazyce C#) nebo Pythonu, abyste mohli volat kvantové operace z klasického programu.

Sada QDK je k dispozici pro víc vývojových prostředí. Vyberte si upřednostňovanou instalaci z následujících možností:

[**Vývoj s využitím aplikací příkazového řádku v Q#** ](xref:microsoft.quantum.install.standalone) – Tento přístup zvolte, pokud chcete pracovat s Q# z příkazového řádku. Tato možnost nevyžaduje ovladač ani hostitelský program jako následující možnosti.

[**Vývoj s využitím poznámkových bloků Jupyter v Q#** ](xref:microsoft.quantum.install.jupyter) – Toto prostředí vyberte, pokud chcete spouštět kód Q# v buňkách s vloženým textem nebo vytvářet interaktivní kurzy kvantových výpočtů. 

[**Vývoj s využitím Q# a Pythonu**](xref:microsoft.quantum.install.python) – Můžete zkombinovat Python a Q# a vytvořit hostitelský program v Pythonu, který volá operace Q#.

[**Vývoj s využitím Q# a .NET**](xref:microsoft.quantum.install.cs) – Zkombinujte jazyk C#, F# nebo VB.NET a Q# a vytvořte hostitelský program v .NET, který volá operace Q#.
