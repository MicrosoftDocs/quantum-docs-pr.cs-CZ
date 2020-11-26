---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195847"
---
# <a name="bitsizei-function"></a>BitSizeI – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pro nezáporné celé číslo `a` vrátí počet bitů, které musí představovat `a` .

To znamená, že vrátí nejmenší $n $, který $a < 2 ^ n $.

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a>Vstup

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Celé číslo, jehož bitová velikost má být vypočítána.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Velikost bitové kopie `a` .