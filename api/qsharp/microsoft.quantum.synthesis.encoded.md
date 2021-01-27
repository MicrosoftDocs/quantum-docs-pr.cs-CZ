---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Encoded – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855487"
---
# <a name="encoded-function"></a>Encoded – funkce

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kódovat tabulku pravdy v {1,-1} kódování

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a>Vstup

### <a name="table--bool"></a>Tabulka: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tabulka pravdy jako pole hodnot hodnoty pravdy



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]

Tabulka pravdy jako pole {1,-1} celých čísel

## <a name="example"></a>Příklad

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```