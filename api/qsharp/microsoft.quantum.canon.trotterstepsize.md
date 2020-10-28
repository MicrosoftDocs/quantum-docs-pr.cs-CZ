---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: fabfbff74572b3c96c701de5443e4265a0468d78
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698796"
---
# <a name="trotterstepsize-function"></a>TrotterStepSize – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vypočítá Trotter velikost kroku v rekurzivní implementaci Trotter algoritmu simulace.

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>Vstup

### <a name="order--int"></a>pořadí: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>Výstup: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Poznámky

Tato operace používá jinou konvenci indexování než [quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139). Konkrétně `DecomposedIntoTimeStepsCA(_, 4)` odpovídá skalární $p _2 (\lambda) $ in quant-pH/0508139.