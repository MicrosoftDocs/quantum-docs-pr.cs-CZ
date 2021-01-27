---
uid: Microsoft.Quantum.Canon.ApplyWithC
title: Operace ApplyWithC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithC
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 393db9f8ce092100abc157ace1ee9fbbb3b06d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850388"
---
# <a name="applywithc-operation"></a>Operace ApplyWithC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dané dvě operace platí pro sebe jako sdružené s druhou.

```qsharp
operation ApplyWithC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl), target : 'T) : Unit is Ctl
```


## <a name="description"></a>Popis

Vzhledem k dvěma operacím, které jsou popsány v rámci $U $ a $V $, jsou použity v sekvenci $U ^ {\dagger} V U $. To znamená, že tato operace implementuje jednotkový operátor, který je dán $V $ sdružený s $U $.

## <a name="input"></a>Vstup

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace $U $, která se má použít pro sdruženou $V $ Všimněte si, že vnější operace $U $ musí být sousední, ale nemusí být ovladatelné.


### <a name="inneroperation--t--unit--is-ctl"></a>innerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

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
- [Microsoft. proApplyWithCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyWithCA)