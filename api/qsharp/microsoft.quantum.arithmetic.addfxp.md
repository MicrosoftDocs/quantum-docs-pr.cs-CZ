---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: Operace AddFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707664"
---
# <a name="addfxp-operation"></a>Operace AddFxP

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Přidá dvě čísla s pevnou desetinnou čárkou uložená v registrech.

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a>Popis

V uvedeném pořadí se dvěma Registry s pevnou desetinnou čárkou ve stavech $ \ket{f_1} $ a $ \ket{f_2} $ provede operace $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $.

## <a name="input"></a>Vstup

### <a name="fp1--fixedpoint"></a>FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

První číslo s pevnou desetinnou čárkou


### <a name="fp2--fixedpoint"></a>FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Druhé číslo s pevnou desetinnou čárkou se aktualizuje tak, aby obsahovalo součet dvou vstupů.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Aktuální implementace vyžaduje, aby dvě čísla s pevnou desetinnou čárkou byla počítána od nejméně významného bitu, tj. $n _i $ a $p _i $ musí být rovna.