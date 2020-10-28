---
uid: Microsoft.Quantum.Canon.NoOp
title: Operace NoOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 987e39577c3b736418234431ed7a915ae461f763
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698948"
---
# <a name="noop-operation"></a>Operace NoOp

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Provede v argumentu operaci identity (No-OP).

```qsharp
operation NoOp<'T> (input : 'T) : Unit
```


## <a name="description"></a>Popis

Tato operace přebírá hodnotu libovolného typu a nedělá k ní nic.
To může být užitečné, kdykoli je očekáván vstup typu operace, ale není nutné provádět žádnou akci.
Například pokud konkrétní oprava chyby Syndrome značí, že nedošlo k žádné chybě, `NoOp<Qubit[]>` může se jednat o správný postup obnovení.
Podobně pokud operace očekává jako vstup proceduru přípravy stavu, dá se `NoOp<Qubit[]>` použít k přípravě stavu $ \ket{0 \cdots 0} $.

## <a name="input"></a>Vstup

### <a name="input--t"></a>vstup: t

Hodnota, která má být ignorována.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="remarks"></a>Poznámky

Ve většině případů je parametr typu pro `NoOp` nutné zadat explicitně. Například `NoOp<Qubit>` je stejný jako <xref:microsoft.quantum.intrinsic.i> .

## <a name="see-also"></a>Viz také

- [Microsoft. stavová. vnitřní. I](xref:Microsoft.Quantum.Intrinsic.I)