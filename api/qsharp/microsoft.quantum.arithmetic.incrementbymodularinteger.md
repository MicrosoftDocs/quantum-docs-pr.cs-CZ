---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Operace IncrementByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 8a02d22facce8f58180752b6d063ac55d75ca537
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222945"
---
# <a name="incrementbymodularinteger-operation"></a>Operace IncrementByModularInteger

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Provede modulární přírůstek qubit registru pomocí celočíselné konstanty.

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Poznamenejte si `increment` $a $, `modulus` pomocí $N $ a celého čísla kódovaného v `target` $y $.
Operace pak provede následující transformaci: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N}. celá čísla \end{align} se kódují ve formátu Little endian.

## <a name="input"></a>Vstup

### <a name="increment--int"></a>přírůstek: [int](xref:microsoft.quantum.lang-ref.int)

Celočíselný přírůstek $a $ se přidá do $y $.


### <a name="modulus--int"></a>Modulus: [int](xref:microsoft.quantum.lang-ref.int)

Integer $N $, který mods $y + a $.


### <a name="target--littleendian"></a>cíl: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Integer $y $ ve `LittleEndian` formátu, `increment` do kterého se $a $ přidá.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Předpokládá, že počáteční hodnota cíle je menší než $N $ a že přírůstek $a $ je menší než $N $.
Všimněte si, že <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implementuje stejnou operaci v `PhaseLittleEndian` závislosti.

## <a name="see-also"></a>Viz také

- [Microsoft. prostředníky. aritmetické. IncrementPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)