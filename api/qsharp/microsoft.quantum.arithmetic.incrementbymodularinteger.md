---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Operace IncrementByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: f5bacef299ab0b3627e757abdcaa798cf9b2e7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846603"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="edb86-102">Operace IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="edb86-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="edb86-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="edb86-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="edb86-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="edb86-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="edb86-105">Provede modulární přírůstek qubit registru pomocí celočíselné konstanty.</span><span class="sxs-lookup"><span data-stu-id="edb86-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="edb86-106">Popis</span><span class="sxs-lookup"><span data-stu-id="edb86-106">Description</span></span>

<span data-ttu-id="edb86-107">Poznamenejte si `increment` $a $, `modulus` pomocí $N $ a celého čísla kódovaného v `target` $y $.</span><span class="sxs-lookup"><span data-stu-id="edb86-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="edb86-108">Operace pak provede následující transformaci: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N}. celá čísla \end{align} se kódují ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="edb86-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="edb86-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="edb86-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="edb86-110">přírůstek: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="edb86-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="edb86-111">Celočíselný přírůstek $a $ se přidá do $y $.</span><span class="sxs-lookup"><span data-stu-id="edb86-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="edb86-112">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="edb86-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="edb86-113">Integer $N $, který mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="edb86-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="edb86-114">cíl: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="edb86-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="edb86-115">Integer $y $ ve `LittleEndian` formátu, `increment` do kterého se $a $ přidá.</span><span class="sxs-lookup"><span data-stu-id="edb86-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="edb86-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="edb86-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="edb86-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="edb86-117">Remarks</span></span>

<span data-ttu-id="edb86-118">Předpokládá, že počáteční hodnota cíle je menší než $N $ a že přírůstek $a $ je menší než $N $.</span><span class="sxs-lookup"><span data-stu-id="edb86-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="edb86-119">Všimněte si, že <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implementuje stejnou operaci v `PhaseLittleEndian` závislosti.</span><span class="sxs-lookup"><span data-stu-id="edb86-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="edb86-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="edb86-120">See Also</span></span>

- [<span data-ttu-id="edb86-121">Microsoft. prostředníky. aritmetické. IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="edb86-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)