---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: Operace ApplyWithInputTransformationCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: b31ed1b3da0d5467588f4cb2e4368e68f0dbe9d5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841113"
---
# <a name="applywithinputtransformationca-operation"></a>Operace ApplyWithInputTransformationCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vzhledem k operaci, která přijímá určitý vstup, funkce, která vrací výstup kompatibilní s touto operací, a vstup k této funkci, používá operaci pomocí funkce k transformaci vstupu na formulář očekávaný operací.

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="fn--u---t"></a>FN: U-> 'T

Funkce, která transformuje daný vstup do formuláře očekávaného operací.


### <a name="op--t--unit--is-adj--ctl"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Operace, která se má použít.


### <a name="input--u"></a>vstup: U

Vstup do funkce.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S


### <a name="u"></a>U



## <a name="example"></a>Příklad

Následující volání používá @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" pro použití operace navržené pro @"Microsoft.Quantum.Arithmetic.BigEndian" vstupy do vstupu typu @"Microsoft.Quantum.Arithmetic.LittleEndian" :

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyWithInputTransformation. Canon.](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. proApplyWithInputTransformationA. Canon.](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [Microsoft. proApplyWithInputTransformationC. Canon.](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [Microsoft. proTransformedOperation. Canon.](xref:Microsoft.Quantum.Canon.TransformedOperation)