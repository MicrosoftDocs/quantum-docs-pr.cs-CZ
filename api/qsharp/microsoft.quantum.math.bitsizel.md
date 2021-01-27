---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: c94d873d7117fd2ee66226fab6d4bfc5b33bc46d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848914"
---
# <a name="bitsizel-function"></a>BitSizeL – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pro nezáporné celé číslo `a` vrátí počet bitů, které musí představovat `a` .

To znamená, že vrátí nejmenší $n $, který $a < 2 ^ n $.

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a>Vstup

### <a name="a--bigint"></a>a: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Celé číslo, jehož bitová velikost má být vypočítána.



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Velikost bitové kopie `a` .