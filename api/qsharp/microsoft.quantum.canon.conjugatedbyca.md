---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: ConjugatedByCA – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 54301f991d3bda14e2d2a0a6837ee89d299f2e04
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840814"
---
# <a name="conjugatedbyca-function"></a>ConjugatedByCA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pro dané vnější a vnitřní operace vrátí novou operaci, která přijedná vnitřní operaci do sdružené operace vnější operací.

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace $U $, která se má použít pro sdruženou $V $ Všimněte si, že vnější operace $U $ musí být sousední, ale nemusí být ovladatelné.


### <a name="inneroperation--t--unit--is-adj--ctl"></a>innerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Operace $V $ je sdružená.



## <a name="output--t--unit--is-adj--ctl"></a>Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Nová operace, jejíž akce je reprezentovaná jednotkou $U ^ {\dagger} V U $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ cíle, na kterém každá z vnitřních a vnějších operací působí.

## <a name="remarks"></a>Poznámky

Vnější operace se vždycky předpokládá jako sousední, ale nemusí být ovladatelné, aby se kombinovaná operace dala řídit.

## <a name="see-also"></a>Viz také

- [Microsoft. proConjugatedByA. Canon.](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft. proConjugatedByC. Canon.](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [Microsoft. proConjugatedByCA. Canon.](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft. proApplyWith. Canon.](xref:Microsoft.Quantum.Canon.ApplyWith)