---
uid: Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator
title: MultiplexerBruteForceFromGenerator – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexerBruteForceFromGenerator
qsharp.summary: >-
  Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: d3606ff4f45765fd3aaf1e6a3078288b214349d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852571"
---
# <a name="multiplexerbruteforcefromgenerator-function"></a>MultiplexerBruteForceFromGenerator – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí jednotkovou operaci řízenou vynásobením $U $, která se vztahuje na jednotkovou $V _j $, pokud je kontrolována v n-qubit čísle stavu $ \ket{j} $.

$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
function MultiplexerBruteForceFromGenerator (unitaryGenerator : (Int, (Int -> (Qubit[] => Unit is Adj + Ctl)))) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="unitarygenerator--intint---qubit--unit--is-adj--ctl"></a>unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL)

Řazená kolekce členů, kde `Int` je prvním prvkem počet unitaries $N $, a druhý prvek `(Int -> ('T => () is Adj + Ctl))` je funkce, která přebírá celé číslo $j $ v $ [0, N-1] $ a vypisuje jednotkovou operaci $V _J $.



## <a name="output--littleendianqubit--unit--is-adj--ctl"></a>Výstup: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Jednotková operace řízená pomocí vícenásobného vynásobení $U $, která se vztahuje na unitaries, kterou popisuje `unitaryGenerator` .

## <a name="see-also"></a>Viz také

- [Microsoft. proMultiplexerBruteForceFromGenerator. Canon.](xref:Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator)