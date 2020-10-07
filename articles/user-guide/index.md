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
ms.openlocfilehash: 81f31a531a1b50ead332bb578ccf392ddced9e8d
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771373"
---
# <a name="the-no-locq-user-guide"></a>Uživatelská příručka jazyka Q#

Vítá vás uživatelská příručka jazyka Q#! 

V různých tématech této příručky najdete podrobný popis základních konceptů jazyka Q# a všechny informace, které potřebujete k psaní kvantových programů.

## <a name="user-guide-contents"></a>Obsah uživatelské příručky

- [Základy Q#](xref:microsoft.quantum.guide.basics): Úvodní přehled účelu a funkcí programovacího jazyka Q#. 

- [Způsoby spuštění programu v Q#Q#](xref:microsoft.quantum.guide.host-programs): Popisuje, jak se spustí program v Q#, a poskytuje přehled různých způsobů volání programu: z příkazového řádku, v aplikacích Jupyter Notebook s podporou Q# nebo z klasického hostitelského programu napsaného v Pythonu nebo v jazyce .NET.

### <a name="no-locq-language"></a>Jazyk Q#

- [Typy v Q#](xref:microsoft.quantum.guide.types): Vysvětluje model typů v jazyce Q# a popisuje syntaxi pro určování typů a práci s nimi.

- [Výrazy typu:](xref:microsoft.quantum.guide.expressions) Podrobně popisuje, jak určovat hodnoty jednotlivých typů v jazyce Q#, odkazovat na ně, kombinovat je a pracovat s nimi. 

### <a name="using-no-locq"></a>Používání akce Q#

- [Struktura souborů v Q#](xref:microsoft.quantum.guide.filestructure): Popisuje strukturu a syntaxi souboru `*.qs` v jazyce Q#.

- [Operace a funkce:](xref:microsoft.quantum.guide.operationsfunctions) Podrobně popisuje dva volatelné typy jazyka Q# – *operace*, které zahrnují akci s qubitovými registry, a *funkce*, které pracují výhradně s klasickými informacemi. 
    Tady uvidíte, jak je definovat a volat, včetně sdružených a řízených verzí kvantových operací.

- [Proměnné:](xref:microsoft.quantum.guide.variables) Popisuje roli proměnných v programech v jazyce Q# a jejich efektivní využití. 
    Tady najdete například informace o rozsazích vazeb, rozdílech mezi neměnnými a proměnlivými proměnnými a postupu jejich přiřazení nebo změně jejich přiřazení.

- [Práce s qubity:](xref:microsoft.quantum.guide.qubits) Popisuje funkce jazyka Q# sloužící k adresování jednotlivých qubitů a systémů qubitů, konkrétně jejich přidělování a měření a provádění operací s nimi. 

- [Tok řízení:](xref:microsoft.quantum.guide.controlflow) Podrobně popisuje programovací vzory toku řízení, které jsou k dispozici v jazyce Q# a mezi které patří řada standardních technik (podmíněné zpracování, smyčky *for* a *while* atd.) a také vzor *Repeat-Until-Success* specifický pro kvantové výpočty.

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
