---
uid: Microsoft.Quantum.Canon.NoOp
title: Operace NoOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 45f3c8c9d4bae8ac8f7f60c4e4f8ead5d92e7c00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852396"
---
# <a name="noop-operation"></a>Operace NoOp

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Provede v argumentu operaci identity (No-OP).

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
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