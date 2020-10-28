---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: Operace ReflectAboutInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706337"
---
# <a name="reflectaboutinteger-operation"></a>Operace ReflectAboutInteger

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Odráží pokladnu v registru o daném klasickém čísle.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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