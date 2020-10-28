---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: ConjugatedByCA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: df29bcf555026bceb13d6896db12e13671a49b9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704329"
---
# <a name="conjugatedbyca-function"></a>ConjugatedByCA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Pro dané vnější a vnitřní operace vrátí novou operaci, která přijedná vnitřní operaci do sdružené operace vnější operací.

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="outeroperation--t--unit-adj"></a>outerOperation: t [=> ADJ](xref:microsoft.quantum.lang-ref.unit)

Operace $U $, která se má použít pro sdruženou $V $ Všimněte si, že vnější operace $U $ musí být sousední, ale nemusí být ovladatelné.


### <a name="inneroperation--t--unit-adj--ctl"></a>innerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operace $V $ je sdružená.



## <a name="output--t--unit-adj--ctl"></a>Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

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