---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: TransformedOperationC – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 9475c5a1cc3b7e14c56c301749311a72e15f71e0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852031"
---
# <a name="transformedoperationc-function"></a>TransformedOperationC – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Výsledkem funkce a operace je nová operace, jejíž vstup je transformovaná pomocí dané funkce.

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a>Vstup

### <a name="fn--u---t"></a>FN: U-> 'T

Funkce, která transformuje daný vstup do formuláře očekávaného operací.


### <a name="op--t--unit--is-ctl"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Operace, která se má transformovat.



## <a name="output--u--unit--is-ctl"></a>Výstup: U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL.

Nová operace tbat volání `fn` s jeho vstupem a pak předává výsledný výstup do `op` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S


### <a name="u"></a>U



## <a name="example"></a>Příklad

Následující volání slouží @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" k transformaci operace navržené pro @"Microsoft.Quantum.Arithmetic.BigEndian" vstupy do operace, která přijímá vstupy typu @"Microsoft.Quantum.Arithmetic.LittleEndian" :

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a>Viz také

- [Microsoft. proTransformedOperation. Canon.](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft. proTransformedOperationA. Canon.](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. proTransformedOperationCA. Canon.](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. proApplyWithInputTransformation. Canon.](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft... Canon. složeno](xref:Microsoft.Quantum.Canon.Composed)