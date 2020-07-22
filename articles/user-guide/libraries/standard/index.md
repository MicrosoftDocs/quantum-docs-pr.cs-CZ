---
title: Úvod do standardních knihoven Microsoft Q#
description: Seznamte se se standardními knihovnami Microsoft Q#, které definují operace, funkce a datové typy používané v kvantových programech.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: ab069c496d89a57f979732da6ccdfbe673b79726
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870579"
---
# <a name="introduction-to-the-q-standard-libraries"></a>Úvod do standardních knihoven Q#

Jazyk Q# je podporován mnoha různými užitečnými operacemi, funkcemi a uživatelem definovanými typy, které tvoří *standardní knihovny* Q#.
[Balíček NuGet `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) nainstalovaný během [instalace a ověření](xref:microsoft.quantum.install) poskytuje kompilátor Q# a části standardní knihovny, které jsou implementovány cílovými počítači.
[Balíček `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) poskytuje část standardních knihoven Q#, které se dají přenášet napříč cílovými počítači.

Symboly definované standardními knihovnami Q# jsou mnohem podrobněji definovány v [dokumentaci k rozhraní API](xref:microsoft.quantum.standardlibsintro).

V následujících částech se seznámíme s nejdůležitějšími funkcemi každé části standardní knihovny a také s tím, jak lze každou funkci používat v praxi.
