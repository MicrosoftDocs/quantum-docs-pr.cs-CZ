---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: Operace MultiplexOperations
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: ad66b39fcfacbe5231ec3b9ba96989d6d5d449c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206098"
---
# <a name="multiplexoperations-operation"></a>Operace MultiplexOperations

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije pole operací řízené polem číselných stavů.

To znamená, že aplikuje jednotkovou operaci řízenou vynásobením $U $, která používá jednotkovou $V _j $, pokud je kontrolována $n $-qubit Number State $ \ket{j} $.

$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="unitaries--t--unit--is-adj--ctl"></a>unitaries: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL []

Pole až do $2 ^ n $ jednotkových operací. Operace $j $ th je indexovaná pomocí číselného stavu $ \ket{j} $ kódovaného ve formátu Little endian.


### <a name="index--littleendian"></a>index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit registr ovládacího prvku, který kóduje číselný stav $ \ket{j} $ ve formátu Little endian.


### <a name="target--t"></a>cíl: t

Obecný registr qubit, na který $V _j $



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="remarks"></a>Poznámky

`coefficients` bude doplněn elementy identity, pokud je zadáno méně než $2 ^ n $. Tato implementace používá pomocná qubits $n-$1.

## <a name="references"></a>Reference

- Směrem k první simulaci nedostatku na více minut s využitím zrychleníů Andrew M. Childs, Dmitri Maslov, Yunseonga, Neilem J. Rossův, jüan Su https://arxiv.org/abs/1711.10980