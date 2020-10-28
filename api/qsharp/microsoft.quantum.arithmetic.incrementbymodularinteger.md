---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Operace IncrementByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 271033b32b0de6cf600dca82126dab19c2bb4f5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707264"
---
# <a name="incrementbymodularinteger-operation"></a>Operace IncrementByModularInteger

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Provede modulární přírůstek qubit registru pomocí celočíselné konstanty.

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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