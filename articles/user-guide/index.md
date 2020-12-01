---
title: Uživatelská příručka jazyka Q#
description: Přehled účelu a obsahu uživatelské příručky
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231753"
---
# <a name="the-no-locq-user-guide"></a>Uživatelská příručka jazyka Q#

Vítá vás uživatelská příručka jazyka Q#! 

V různých tématech této příručky uvádíme některé základy k vývoji kvantových programů pomocí jazyka Q#.

Úplnou specifikaci a dokumentaci programovacího jazyka Q# najdete v [příručce k jazyku Q#](xref:microsoft.quantum.qsharp.index). 

## <a name="user-guide-contents"></a>Obsah uživatelské příručky

- [Programy Q#](xref:microsoft.quantum.guide.programs): Rychlý úvod do kvantových programům v jazyce Q#. 

- [Způsoby spuštění programu v Q#Q#](xref:microsoft.quantum.guide.host-programs): Popisuje, jak se spustí program v Q#, a poskytuje přehled různých způsobů volání programu: z příkazového řádku, v aplikacích Jupyter Notebook s podporou Q# nebo z klasického hostitelského programu napsaného v Pythonu nebo v jazyce .NET.

- [Testování a ladění:](xref:microsoft.quantum.guide.testingdebugging) Podrobně popisuje některé techniky k zajištění, že váš kód dělá to, co by měl. 
    Z důvodu obecné neprůhlednosti kvantových informací může ladění kvantového programu vyžadovat specializované techniky. 
    Naštěstí jazyk Q# podporuje mnoho technik klasického ladění, na které jsou programátoři zvyklí, a také ty, které jsou specifické pro kvantové výpočty. Patří mezi ně vytváření a spouštění testů jednotek v jazyce Q#, vkládání *kontrolních výrazů* pro hodnoty a pravděpodobnosti do kódu a funkce `Dump`, které vypisují stavy cílových počítačů. 
    Tyto funkce se dají použít společně s naším simulátorem celkového stavu k ladění určitých částí výpočtů obcházením některých kvantových omezení (např. [teorému o nemožnosti klonování](xref:microsoft.quantum.concepts.pauli)).

### <a name="quantum-simulators-and-resource-estimators"></a>Kvantové simulátory a estimátory prostředků

- [Kvantové simulátory a hostitelské aplikace:](xref:microsoft.quantum.machines) Přehled různých dostupných simulátorů a také způsobu, jakým hostitelské programy a cílové počítače spolupracují při spouštění programů v Q#.

- [Simulátor celkového stavu:](xref:microsoft.quantum.machines.full-state-simulator) Cílový počítač, který simuluje celkový kvantový stav. Tento simulátor je užitečný při úplném spouštění nebo ladění menších programů (méně než pár desítek qubitů).

- [Estimátor prostředků:](xref:microsoft.quantum.machines.resources-estimator) Odhaduje prostředky potřebné ke spuštění konkrétní instance operace Q# na kvantovém počítači.

- [Simulátor trasování:](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Spouští kvantové programy, aniž by ve skutečnosti simuloval stav kvantového počítače, a díky tomu může spouštět kvantové programy využívající tisíce qubitů. Tento simulátor je užitečný při ladění klasického kódu v rámci kvantového programu a také při odhadu potřebných prostředků.

- [Simulátor Toffoli:](xref:microsoft.quantum.machines.toffoli-simulator) Kvantový simulátor pro zvláštní účely, který je možné používat s miliony qubitů, ale pouze pro programy s omezenou sadou kvantových operací (konkrétně operací X, CNOT a vícenásobně řízených operací X).

### <a name="quick-reference-pages"></a>Stručné referenční stránky

- [Příkazy magic IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): Stručná referenční stránka pro příkazy magic IQ# v aplikací Jupyter Notebook s podporou Q#.
