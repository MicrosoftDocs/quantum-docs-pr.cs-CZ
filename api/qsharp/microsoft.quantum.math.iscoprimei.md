---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708374"
---
# <a name="iscoprimei-function"></a>IsCoprimeI – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček [](https://nuget.org/packages/)


Vrátí hodnotu true, pokud $a $ a $b $ jsou souběžné a false v opačném případě.

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Vstup

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

první počet primality, které se testují společně


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

druhý počet, který provádí testování primality



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

True, pokud $a $ a $b $ jsou souběžné (například jejich největší společný dělitel je 1) a jinak false