---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: Operace ReflectAboutInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: 4d451c4e8e002f86c892b394f58ea2d7e9dd6a48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842980"
---
# <a name="reflectaboutinteger-operation"></a>Operace ReflectAboutInteger

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Odráží pokladnu v registru o daném klasickém čísle.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Vzhledem k prvnímu zaregistrování do stavu $ \ sum_i \ alpha_i \ket{i} $, kde každý $ \ket{i} $ je základní stav reprezentující celé číslo $i $, odráží stav registru pro základní stav pro dané celé číslo $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {IJ}} \ alpha_i \ket{i} $ $

## <a name="input"></a>Vstup

### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)

Klasické celé číslo, které indexuje základní stav, o který se má odrážet.


### <a name="reg--littleendian"></a>REG: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Tato operace je implementována místně bez explicitního přidělení dalších pomocných qubits.