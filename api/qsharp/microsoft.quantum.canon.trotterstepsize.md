---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840077"
---
# <a name="trotterstepsize-function"></a>TrotterStepSize – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vypočítá Trotter velikost kroku v rekurzivní implementaci Trotter algoritmu simulace.

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>Vstup

### <a name="order--int"></a>pořadí: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Poznámky

Tato operace používá jinou konvenci indexování než [quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139). Konkrétně `DecomposedIntoTimeStepsCA(_, 4)` odpovídá skalární $p _2 (\lambda) $ in quant-pH/0508139.