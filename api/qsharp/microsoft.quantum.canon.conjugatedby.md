---
uid: Microsoft.Quantum.Canon.ConjugatedBy
title: ConjugatedBy – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedBy
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: c11e6b2cc97e682bf4fe266997f60ce69e87ba96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840874"
---
# <a name="conjugatedby-function"></a>ConjugatedBy – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pro dané vnější a vnitřní operace vrátí novou operaci, která přijedná vnitřní operaci do sdružené operace vnější operací.

```qsharp
function ConjugatedBy<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit)) : ('T => Unit)
```


## <a name="input"></a>Vstup

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace $U $, která se má použít pro sdruženou $V $ Všimněte si, že vnější operace $U $ musí být sousední, ale nemusí být ovladatelné.


### <a name="inneroperation--t--unit"></a>innerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace $V $ je sdružená.



## <a name="output--t--unit"></a>Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

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