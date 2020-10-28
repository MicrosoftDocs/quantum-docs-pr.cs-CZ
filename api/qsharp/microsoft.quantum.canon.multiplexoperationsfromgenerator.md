---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: Operace MultiplexOperationsFromGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 2fde0bf391568f39128e6dca4b535aa6b78407c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698960"
---
# <a name="multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="b6b24-102">Operace MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="b6b24-102">MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="b6b24-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b6b24-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b6b24-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6b24-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6b24-105">Aplikuje jednotkovou operaci řízenou vynásobením $U $, která se vztahuje na jednotkovou $V _j $, pokud se řídí hodnotou n-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="b6b24-105">Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="b6b24-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="b6b24-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="b6b24-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="b6b24-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit-adj--ctl"></a><span data-ttu-id="b6b24-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> 't => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="b6b24-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

<span data-ttu-id="b6b24-109">Řazená kolekce členů, kde `Int` je prvním prvkem počet unitaries $N $, a druhý prvek `(Int -> ('T => () is Adj + Ctl))` je funkce, která přebírá celé číslo $j $ v $ [0, N-1] $ a vypisuje jednotkovou operaci $V _J $.</span><span class="sxs-lookup"><span data-stu-id="b6b24-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="b6b24-110">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b6b24-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b6b24-111">$n $-qubit registr ovládacího prvku, který kóduje číselný stav $ \ket{j} $ ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="b6b24-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="b6b24-112">cíl: t</span><span class="sxs-lookup"><span data-stu-id="b6b24-112">target : 'T</span></span>

<span data-ttu-id="b6b24-113">Obecný registr qubit, na který $V _j $</span><span class="sxs-lookup"><span data-stu-id="b6b24-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b6b24-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6b24-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b6b24-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b6b24-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b6b24-116">'S</span><span class="sxs-lookup"><span data-stu-id="b6b24-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="b6b24-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b6b24-117">Remarks</span></span>

<span data-ttu-id="b6b24-118">`coefficients` bude doplněn elementy identity, pokud je zadáno méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="b6b24-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="b6b24-119">Tato implementace používá pomocná qubits $n-$1.</span><span class="sxs-lookup"><span data-stu-id="b6b24-119">This implementation uses $n-1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="b6b24-120">Odkazy</span><span class="sxs-lookup"><span data-stu-id="b6b24-120">References</span></span>

- [<span data-ttu-id="b6b24-121">*Andrew M. Childs, Dmitri Maslov, Yunseong, Neilem J. Rossův, jüan Su* , arXiv: 1711.10980</span><span class="sxs-lookup"><span data-stu-id="b6b24-121"> *Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su* , arXiv:1711.10980</span></span>](https://arxiv.org/abs/1711.10980)