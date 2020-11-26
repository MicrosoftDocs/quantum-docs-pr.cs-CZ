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
# <a name="multiplexoperations-operation"></a><span data-ttu-id="5f450-102">Operace MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="5f450-102">MultiplexOperations operation</span></span>

<span data-ttu-id="5f450-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5f450-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5f450-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5f450-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5f450-105">Použije pole operací řízené polem číselných stavů.</span><span class="sxs-lookup"><span data-stu-id="5f450-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="5f450-106">To znamená, že aplikuje jednotkovou operaci řízenou vynásobením $U $, která používá jednotkovou $V _j $, pokud je kontrolována $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="5f450-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="5f450-107">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="5f450-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5f450-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="5f450-108">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="5f450-109">unitaries: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="5f450-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="5f450-110">Pole až do $2 ^ n $ jednotkových operací.</span><span class="sxs-lookup"><span data-stu-id="5f450-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="5f450-111">Operace $j $ th je indexovaná pomocí číselného stavu $ \ket{j} $ kódovaného ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="5f450-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="5f450-112">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5f450-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5f450-113">$n $-qubit registr ovládacího prvku, který kóduje číselný stav $ \ket{j} $ ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="5f450-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="5f450-114">cíl: t</span><span class="sxs-lookup"><span data-stu-id="5f450-114">target : 'T</span></span>

<span data-ttu-id="5f450-115">Obecný registr qubit, na který $V _j $</span><span class="sxs-lookup"><span data-stu-id="5f450-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5f450-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5f450-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5f450-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5f450-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5f450-118">'S</span><span class="sxs-lookup"><span data-stu-id="5f450-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="5f450-119">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5f450-119">Remarks</span></span>

<span data-ttu-id="5f450-120">`coefficients` bude doplněn elementy identity, pokud je zadáno méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="5f450-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="5f450-121">Tato implementace používá pomocná qubits $n-$1.</span><span class="sxs-lookup"><span data-stu-id="5f450-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="5f450-122">Reference</span><span class="sxs-lookup"><span data-stu-id="5f450-122">References</span></span>

- <span data-ttu-id="5f450-123">Směrem k první simulaci nedostatku na více minut s využitím zrychleníů Andrew M. Childs, Dmitri Maslov, Yunseonga, Neilem J. Rossův, jüan Su https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="5f450-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>