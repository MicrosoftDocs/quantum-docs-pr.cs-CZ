---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: Operace IncrementPhaseByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 6a39ce49dfa28c1f1cbe6b29e526144c3ac19e53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222877"
---
# <a name="incrementphasebymodularinteger-operation"></a>Operace IncrementPhaseByModularInteger

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Provede modulární přírůstek qubit registru pomocí celočíselné konstanty.

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Poznamenejte si `increment` $a $, `modulus` pomocí $N $ a celého čísla kódovaného v `target` $y $.
Operace pak provede následující transformaci: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} v \end{align} se ve formátu Little endian kódují.

## <a name="input"></a>Vstup

### <a name="increment--int"></a>přírůstek: [int](xref:microsoft.quantum.lang-ref.int)

Celočíselný přírůstek $a $ se přidá do $y $.


### <a name="modulus--int"></a>Modulus: [int](xref:microsoft.quantum.lang-ref.int)

Integer $N $, který mods $y + a $.


### <a name="target--phaselittleendian"></a>cíl: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Celé číslo $y $ ve formátu Little-endian, který je zakódovaný `increment` do $a $ je přidaný do.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Předpokládá, že `target` má nejvyšší bit nastavený na hodnotu 0.
Také předpokládá, že hodnota cíle je menší než $N $.

V diagramu okruhu a vysvětlení, viz obrázek 5 na [stránce 5 arXiv: quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).

## <a name="see-also"></a>Viz také

- [Microsoft. prostředníky. aritmetické. IncrementByModularInteger](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)