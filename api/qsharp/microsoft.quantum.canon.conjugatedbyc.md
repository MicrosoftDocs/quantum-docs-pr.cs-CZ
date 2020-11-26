---
uid: Microsoft.Quantum.Canon.ConjugatedByC
title: ConjugatedByC – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByC
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 1aa471a0f9039151d130bd52a026f4c1a0765e32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216672"
---
# <a name="conjugatedbyc-function"></a>ConjugatedByC – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pro dané vnější a vnitřní operace vrátí novou operaci, která přijedná vnitřní operaci do sdružené operace vnější operací.

```qsharp
function ConjugatedByC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl)) : ('T => Unit is Ctl)
```


## <a name="input"></a>Vstup

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace $U $, která se má použít pro sdruženou $V $ Všimněte si, že vnější operace $U $ musí být sousední, ale nemusí být ovladatelné.


### <a name="inneroperation--t--unit--is-ctl"></a>innerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Operace $V $ je sdružená.



## <a name="output--t--unit--is-ctl"></a>Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Nová operace, jejíž akce je reprezentovaná jednotkou $U ^ {\dagger} V U $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ cíle, na kterém každá z vnitřních a vnějších operací působí.

## <a name="remarks"></a>Poznámky

Vnější operace se vždycky předpokládá jako sousední, ale nemusí být ovladatelné, aby se kombinovaná operace dala řídit.

## <a name="see-also"></a>Viz také

- [Microsoft. proConjugatedBy. Canon.](xref:Microsoft.Quantum.Canon.ConjugatedBy)
- [Microsoft. proConjugatedByA. Canon.](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft. proConjugatedByCA. Canon.](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft. proApplyWith. Canon.](xref:Microsoft.Quantum.Canon.ApplyWith)