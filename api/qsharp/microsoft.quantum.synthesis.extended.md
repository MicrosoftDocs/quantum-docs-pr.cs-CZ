---
uid: Microsoft.Quantum.Synthesis.Extended
title: Rozšířená funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855475"
---
# <a name="extended-function"></a>Rozšířená funkce

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rozšiřuje spektrum o opačné koeficienty.

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a>Vstup

### <a name="spectrum--int"></a>spektrum: [int](xref:microsoft.quantum.lang-ref.int)[]

Spektrální koeficienty



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]

Koeficienty následované opačným kopírováním

## <a name="example"></a>Příklad

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```