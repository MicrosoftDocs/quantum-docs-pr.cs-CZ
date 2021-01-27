---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834190"
---
# <a name="boolarrayasresultarray-function"></a>BoolArrayAsResultArray – funkce

Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Převede `Bool[]` typ na `Result[]` typ, kde `true` je mapován na `One` a `false` je mapován na `Zero` .

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a>Vstup

### <a name="input--bool"></a>vstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` má být převedeno.



## <a name="output--__invalidresult__"></a>Výstup: __neplatný <Result>__[]

`Result[]`Představuje `input` .