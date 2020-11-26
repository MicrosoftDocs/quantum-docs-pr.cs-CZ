---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: d6566716f5a63c090668d9582b7b000c16d1f6a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231088"
---
# <a name="integerbits-function"></a>IntegerBits – funkce

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí všechny pozice, ve kterých jsou nastaveny bity celého čísla.

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a>Vstup

### <a name="value--int"></a>hodnota: [int](xref:microsoft.quantum.lang-ref.int)

Nezáporné číslo.


### <a name="length--int"></a>Délka: [int](xref:microsoft.quantum.lang-ref.int)

Počet bitů v binárním rozbalování `value` .



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole obsahující všechny bitové pozice (počínaje 0), které jsou 1 v binárním rozšíření s `value` ohledem na všechny bity až do pozice `length - 1` .  Všechny pozice jsou seřazené v poli podle pozice v rostoucím pořadí.