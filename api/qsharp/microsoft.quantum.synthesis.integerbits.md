---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855405"
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

## <a name="example"></a>Příklad

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```