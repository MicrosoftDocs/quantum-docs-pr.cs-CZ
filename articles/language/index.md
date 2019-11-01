---
title: Programovací jazyk Q# | Microsoft Docs
description: Programovací jazyk Q#
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: d8759b9f043d2e13f4b0c97d54bd824c7e87d6de
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035261"
---
# <a name="the-q-programming-language"></a>Programovací jazyk Q#

# <a name="introduction"></a>Úvod

Přirozeným modelem pro kvantové výpočty je přistupovat ke kvantovému počítači jako ke koprocesoru podobnému těm, které se používají s grafickými procesory, programovatelnými hradlovými poli (FPGA) a dalšími pomocnými procesory.
Primární řídicí logika spouští klasický kód v klasickém „hostitelském“ počítači.
Když je to vhodné a potřebné, hostitelský program může vyvolat subrutinu, která běží na pomocném procesoru.
Po dokončení provádění subrutiny získá hostitelský program přístup k jejím výsledkům.

Q# je programovací jazyk specifický pro konkrétní doménu, který se používá k vyjadřování kvantových algoritmů.
Slouží k psaní subrutin, které se spouštějí na pomocném kvantovém procesoru a jsou řízeny klasickým hostitelským programem a počítačem.
Dokud nebudou kvantové procesory běžně k dispozici, budou se subrutiny v jazyku Q# spouštět v simulátoru.

Jazyk Q# poskytuje malou množinu primitivních typů a také dva způsoby (pole a řazené kolekce členů) vytváření nových strukturovaných typů.
Podporuje základní procedurální model pro psaní programů se smyčkami a příkazy if/then.
Konstrukty nejvyšší úrovně v jazyku Q# jsou uživatelsky definované typy, operace a funkce.

V následujících částech jsou podrobně vysvětlena tato témata:
- [Model typů](xref:microsoft.quantum.language.type-model)
- [Výrazy](xref:microsoft.quantum.language.expressions)
- [Příkazy](xref:microsoft.quantum.language.statements)
- [Struktura souborů](xref:microsoft.quantum.language.file-structure)

# <a name="conventions"></a>Zásady

Snažíme se zajistit, aby se ve všech situacích konzistentně používaly běžná interpunkční znaménka.
Očekáváme, že díky tomu bude snazší naučit se jazyk Q# a číst ho, protože tato znaménka znamenají vždy totéž a stejná koncepce je vždy reprezentována stejným způsobem.

Konkrétně:

- Středník (`;`) slouží k ukončení příkazu nebo jednořádkové direktivy.
  Nepoužívá se k žádným jiným účelům.
- Čárka (`,`) slouží k oddělení prvků posloupnosti. Používá se pro literály řazené kolekce členů, literály pole, seznamy argumentů, definice řazených kolekcí členů a seznamy typů. **Na rozdíl od dřívějších verzí již znak `;` není podporován jako oddělovač literálů pole.**
- Dvojtečka (`:`) slouží k uvedení anotace typu. Používá se primárně v signaturách, které lze volat.
  Vzhledem k tomu, že dvojtečka vždy uvádí signaturu typu, ternární podmíněný operátor zavedený ve verzi 0.3 používá svislou čáru (`|`) pro oddělení hodnot true a false; jazyk Q# proto používá namísto dvojtečky oddělovač `cond ? tval | fval` jako v jazyku C.
  
