---
uid: Microsoft.Quantum.Arrays.Merged
title: Sloučená funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845615"
---
# <a name="merged-function"></a>Sloučená funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


U dvou seřazených polí vrátí jedno pole obsahující prvky obou v setříděném pořadí. Používá se interně slučovacím řazením.

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a>Vstup

### <a name="comparison--tt---bool"></a>porovnání: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="left--t"></a>Left: t []




### <a name="right--t"></a>Right: t []





## <a name="output--t"></a>Výstup: t []



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

