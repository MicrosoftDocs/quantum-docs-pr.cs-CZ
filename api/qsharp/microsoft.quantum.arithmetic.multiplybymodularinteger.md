---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Operace MultiplyByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706392"
---
# <a name="multiplybymodularinteger-operation"></a>Operace MultiplyByModularInteger

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Provede modulární násobení pomocí celočíselné konstanty v qubit registru.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Popis

Poznamenejte si je `modulus` $N $ a `constMultiplier` pomocí $a $.
Tato operace pak implementuje jednotnou operaci definovanou na základě následujícího mapování na výpočetní bázi: $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ pro všechny $y $ mezi $0 $ a $N-$1.

## <a name="input"></a>Vstup

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Konstanta, o kterou se násobí násobitel. Musí být souběžně s modulem.


### <a name="modulus--int"></a>Modulus: [int](xref:microsoft.quantum.lang-ref.int)

Operace násobení je prováděna modulo `modulus` .


### <a name="multiplier--littleendian"></a>násobitel: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Číslo vynásobené konstantou.
Toto je pole qubits kódování celé číslo ve formátu Little endian.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

- Pro diagram okruhu a vysvětlení viz obrázek 7 na [stránce 8 arXiv: quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)
- Tato operace odpovídá ₐ U v [arXiv: quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)