---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: Operace IncrementPhaseByInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: cc7922b2940cb979394958d5eb4e9933144eb062
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843153"
---
# <a name="incrementphasebyinteger-operation"></a>Operace IncrementPhaseByInteger

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zvýší nepodepsaná bezplatných hodnot do registru pomocí klasického celého čísla pomocí otočení fáze.

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Předpokládejme, že `target` kódování unsigned integer $x $ v kódování Little endian a `increment` je rovno $a $.
Tato operace pak implementuje jednotkové $ \ket{x} \mapsto \ket{x + a} $, kde sčítání se provádí modulo $2 ^ n $, kde $n = \texttt{Length (Target!)} $.

## <a name="input"></a>Vstup

### <a name="increment--int"></a>přírůstek: [int](xref:microsoft.quantum.lang-ref.int)

Celé číslo, kterým `target` se zvyšuje hodnota.


### <a name="target--phaselittleendian"></a>cíl: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

V poli pro duální (QFT) se registruje při kódování nenáročného využívání unsigned integer.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Všimněte si, že jsme tento okruh zjednodušili, protože přírůstek je klasická konstanta, ne Pokladna za sebou.

Podívejte se na obrázek na [ stránce 6 arXiv: quant-pH/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) pro diagram okruhu a vysvětlení.

## <a name="references"></a>Reference

- [*Tomáš G. Draper*, arXiv: quant-pH/0008033](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a>Viz také

- [Microsoft. prostředníky. aritmetické. IncrementByInteger](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)