---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 21c9cdfc3b5b266cb3b93e52ee2fa4c655caf795
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698821"
---
# <a name="transformedoperationca-function"></a>TransformedOperationCA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Výsledkem funkce a operace je nová operace, jejíž vstup je transformovaná pomocí dané funkce.

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="fn--u---t"></a>FN: U-> 'T

Funkce, která transformuje daný vstup do formuláře očekávaného operací.


### <a name="op--t--unit-adj--ctl"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operace, která se má transformovat.



## <a name="output--u--unit-adj--ctl"></a>Výstup: U => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Nová operace tbat volání `fn` s jeho vstupem a pak předává výsledný výstup do `op` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S


### <a name="u"></a>U



## <a name="see-also"></a>Viz také

- [Microsoft. proTransformedOperation. Canon.](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft. proTransformedOperationA. Canon.](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. proTransformedOperationCA. Canon.](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. proApplyWithInputTransformation. Canon.](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft... Canon. složeno](xref:Microsoft.Quantum.Canon.Composed)