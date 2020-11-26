---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: Operace MultiplexOperationsBruteForceFromGenerator
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: a700cffbd8fe8be01fdb7344cc9d4b02a4900174
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205996"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a><span data-ttu-id="976af-102">Operace MultiplexOperationsBruteForceFromGenerator</span><span class="sxs-lookup"><span data-stu-id="976af-102">MultiplexOperationsBruteForceFromGenerator operation</span></span>

<span data-ttu-id="976af-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="976af-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="976af-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="976af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="976af-105">Aplikuje jednotkovou operaci řízenou vynásobením $U $, která se vztahuje na jednotkovou $V _j $ při kontrole pomocí n-qubit čísla stavu $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="976af-105">Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="976af-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="976af-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="976af-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="976af-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="976af-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="976af-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="976af-109">Řazená kolekce členů, kde `Int` je prvním prvkem počet unitaries $N $, a druhý prvek `(Int -> ('T => () is Adj + Ctl))` je funkce, která přebírá celé číslo $j $ v $ [0, N-1] $ a vypisuje jednotkovou operaci $V _J $.</span><span class="sxs-lookup"><span data-stu-id="976af-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="976af-110">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="976af-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="976af-111">$n $-qubit registr ovládacího prvku, který kóduje číselný stav $ \ket{j} $ ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="976af-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="976af-112">cíl: t</span><span class="sxs-lookup"><span data-stu-id="976af-112">target : 'T</span></span>

<span data-ttu-id="976af-113">Obecný registr qubit, na který $V _j $</span><span class="sxs-lookup"><span data-stu-id="976af-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="976af-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="976af-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="976af-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="976af-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="976af-116">'S</span><span class="sxs-lookup"><span data-stu-id="976af-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="976af-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="976af-117">Remarks</span></span>

<span data-ttu-id="976af-118">`coefficients` bude doplněn elementy identity, pokud je zadáno méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="976af-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="976af-119">Tato verze je implementována přímo prostřednictvím smyčky v rámci jednotně řízených operátorů n.</span><span class="sxs-lookup"><span data-stu-id="976af-119">This version is implemented directly by looping through n-controlled unitary operators.</span></span>