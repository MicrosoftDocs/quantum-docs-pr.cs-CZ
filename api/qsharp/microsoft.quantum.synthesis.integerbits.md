---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706425"
---
# <a name="integerbits-function"></a>IntegerBits – funkce

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček [](https://nuget.org/packages/)


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