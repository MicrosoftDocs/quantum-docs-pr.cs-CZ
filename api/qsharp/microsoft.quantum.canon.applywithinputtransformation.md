---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Operace ApplyWithInputTransformation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 2b7863337ef724d9c3ba10201a9a01d0b2226ea8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704568"
---
# <a name="applywithinputtransformation-operation"></a>Operace ApplyWithInputTransformation

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vzhledem k operaci, která přijímá určitý vstup, funkce, která vrací výstup kompatibilní s touto operací, a vstup k této funkci, používá operaci pomocí funkce k transformaci vstupu na formulář očekávaný operací.

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a>Vstup

### <a name="fn--u---t"></a>FN: U-> 'T

Funkce, která transformuje daný vstup do formuláře očekávaného operací.


### <a name="op--t--unit"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která se má použít.


### <a name="input--u"></a>vstup: U

Vstup do funkce.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S


### <a name="u"></a>U



## <a name="see-also"></a>Viz také

- [Microsoft. proApplyWithInputTransformationA. Canon.](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [Microsoft. proApplyWithInputTransformationC. Canon.](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [Microsoft. proApplyWithInputTransformationCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [Microsoft. proTransformedOperation. Canon.](xref:Microsoft.Quantum.Canon.TransformedOperation)