---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: Operace ApplyWithCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: abc62791416e78c1b2937a226327b71da8b8e288
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704577"
---
# <a name="applywithca-operation"></a>Operace ApplyWithCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Dané dvě operace platí pro sebe jako sdružené s druhou.

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit
```


## <a name="description"></a>Popis

Vzhledem k dvěma operacím, které jsou popsány v rámci $U $ a $V $, jsou použity v sekvenci $U ^ {\dagger} V U $. To znamená, že tato operace implementuje jednotkový operátor, který je dán $V $ sdružený s $U $.

## <a name="input"></a>Vstup

### <a name="outeroperation--t--unit-adj"></a>outerOperation: t [=> ADJ](xref:microsoft.quantum.lang-ref.unit)

Operace $U $, která se má použít pro sdruženou $V $ Všimněte si, že vnější operace $U $ musí být sousední, ale nemusí být ovladatelné.


### <a name="inneroperation--t--unit-adj--ctl"></a>innerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operace $V $ je sdružená.


### <a name="target--t"></a>cíl: t

Vstup, který má být poskytnut vnější a vnitřní operaci.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Cíl, na kterém každá z vnitřních a vnějších operací působí.

## <a name="remarks"></a>Poznámky

Vnější operace se vždycky předpokládá jako sousední, ale nemusí být ovladatelné, aby se kombinovaná operace dala řídit.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyWith. Canon.](xref:Microsoft.Quantum.Canon.ApplyWith)
- [Microsoft. proApplyWithA. Canon.](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [Microsoft. proApplyWithC. Canon.](xref:Microsoft.Quantum.Canon.ApplyWithC)