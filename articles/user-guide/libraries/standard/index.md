---
title: Úvod do standardních knihoven Microsoft Q#
description: Seznamte se se standardními knihovnami Microsoft Q#, které definují operace, funkce a datové typy používané v kvantových programech.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 63709015a12a7f972a676018970143ca163e92d0
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836008"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Úvod do standardních knihoven Q#

Jazyk Q# je podporován mnoha různými užitečnými operacemi, funkcemi a uživatelem definovanými typy, které tvoří *standardní knihovny* Q#.
[Balíček NuGet `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) nainstalovaný během [instalace a ověření](xref:microsoft.quantum.install) poskytuje kompilátor Q# a části standardní knihovny, které jsou implementovány cílovými počítači.
[Balíček `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) poskytuje část standardních knihoven Q#, které se dají přenášet napříč cílovými počítači.

Symboly definované standardními knihovnami Q# jsou mnohem podrobněji definovány v [dokumentaci k rozhraní API](xref:microsoft.quantum.apiref-intro).

V následujících částech se seznámíme s nejdůležitějšími funkcemi každé části standardní knihovny a také s tím, jak lze každou funkci používat v praxi.
