---
uid: Microsoft.Quantum.Canon.MultiplexerFromGenerator
title: MultiplexerFromGenerator – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexerFromGenerator
qsharp.summary: >-
  Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: f9382d7d10beeee92dde63ab8db8bf6e4c8305d0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206149"
---
# <a name="multiplexerfromgenerator-function"></a><span data-ttu-id="f2af9-102">MultiplexerFromGenerator – funkce</span><span class="sxs-lookup"><span data-stu-id="f2af9-102">MultiplexerFromGenerator function</span></span>

<span data-ttu-id="f2af9-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f2af9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f2af9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2af9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2af9-105">Vrátí jednotkovou operaci řízenou vynásobením $U $, která se vztahuje na jednotkovou $V _j $, pokud je kontrolována v n-qubit čísle stavu $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="f2af9-105">Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="f2af9-106">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="f2af9-106">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
function MultiplexerFromGenerator (unitaryGenerator : (Int, (Int -> (Qubit[] => Unit is Adj + Ctl)))) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="f2af9-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="f2af9-107">Input</span></span>

### <a name="unitarygenerator--intint---qubit--unit--is-adj--ctl"></a><span data-ttu-id="f2af9-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="f2af9-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="f2af9-109">Řazená kolekce členů, kde `Int` je prvním prvkem počet unitaries $N $, a druhý prvek `(Int -> ('T => () is Adj + Ctl))` je funkce, která přebírá celé číslo $j $ v $ [0, N-1] $ a vypisuje jednotkovou operaci $V _J $.</span><span class="sxs-lookup"><span data-stu-id="f2af9-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>



## <a name="output--littleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="f2af9-110">Výstup: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f2af9-110">Output : ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f2af9-111">Jednotková operace řízená pomocí vícenásobného vynásobení $U $, která se vztahuje na unitaries, kterou popisuje `unitaryGenerator` .</span><span class="sxs-lookup"><span data-stu-id="f2af9-111">A multiply-controlled unitary operation $U$ that applies unitaries described by `unitaryGenerator`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2af9-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="f2af9-112">See Also</span></span>

- [<span data-ttu-id="f2af9-113">Microsoft. proMultiplexOperationsFromGenerator. Canon.</span><span class="sxs-lookup"><span data-stu-id="f2af9-113">Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)