---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: d8c2f52290ce89d0a8ff138ba25f6b2e5e0516d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698828"
---
# <a name="transformedoperation-function"></a>TransformedOperation – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Výsledkem funkce a operace je nová operace, jejíž vstup je transformovaná pomocí dané funkce.

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a>Vstup

### <a name="fn--u---t"></a>FN: U-> 'T

Funkce, která transformuje daný vstup do formuláře očekávaného operací.


### <a name="op--t--unit"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která se má transformovat.



## <a name="output--u--unit"></a>Výstup: ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Nová operace tbat volání `fn` s jeho vstupem a pak předává výsledný výstup do `op` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S


### <a name="u"></a>U



## <a name="see-also"></a>Viz také

- [Microsoft. proTransformedOperationA. Canon.](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. proTransformedOperationC. Canon.](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [Microsoft. proTransformedOperationCA. Canon.](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. proApplyWithInputTransformation. Canon.](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft... Canon. složeno](xref:Microsoft.Quantum.Canon.Composed)