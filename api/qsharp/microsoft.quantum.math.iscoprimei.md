---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 53131a755571ad1ac0a8a984bf229b16f67dbe51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195354"
---
# <a name="iscoprimei-function"></a>IsCoprimeI – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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