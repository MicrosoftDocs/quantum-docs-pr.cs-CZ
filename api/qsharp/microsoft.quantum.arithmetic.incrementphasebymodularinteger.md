---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: Operace IncrementPhaseByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 52309c056a3eae25ffdfbfa848f94bf744c71132
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707233"
---
# <a name="incrementphasebymodularinteger-operation"></a><span data-ttu-id="a5232-102">Operace IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="a5232-102">IncrementPhaseByModularInteger operation</span></span>

<span data-ttu-id="a5232-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a5232-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a5232-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5232-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5232-105">Provede modulární přírůstek qubit registru pomocí celočíselné konstanty.</span><span class="sxs-lookup"><span data-stu-id="a5232-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="a5232-106">Popis</span><span class="sxs-lookup"><span data-stu-id="a5232-106">Description</span></span>

<span data-ttu-id="a5232-107">Poznamenejte si `increment` $a $, `modulus` pomocí $N $ a celého čísla kódovaného v `target` $y $.</span><span class="sxs-lookup"><span data-stu-id="a5232-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="a5232-108">Operace pak provede následující transformaci: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} v \end{align} se ve formátu Little endian kódují.</span><span class="sxs-lookup"><span data-stu-id="a5232-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format in QFT basis.</span></span>

## <a name="input"></a><span data-ttu-id="a5232-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="a5232-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="a5232-110">přírůstek: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a5232-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a5232-111">Celočíselný přírůstek $a $ se přidá do $y $.</span><span class="sxs-lookup"><span data-stu-id="a5232-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="a5232-112">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a5232-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a5232-113">Integer $N $, který mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="a5232-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="a5232-114">cíl: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a5232-114">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="a5232-115">Celé číslo $y $ ve formátu Little-endian, který je zakódovaný `increment` do $a $ je přidaný do.</span><span class="sxs-lookup"><span data-stu-id="a5232-115">Integer $y$ in phase-encoded little-endian format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a5232-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5232-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a5232-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a5232-117">Remarks</span></span>

<span data-ttu-id="a5232-118">Předpokládá, že `target` má nejvyšší bit nastavený na hodnotu 0.</span><span class="sxs-lookup"><span data-stu-id="a5232-118">Assumes that `target` has the highest bit set to 0.</span></span>
<span data-ttu-id="a5232-119">Také předpokládá, že hodnota cíle je menší než $N $.</span><span class="sxs-lookup"><span data-stu-id="a5232-119">Also assumes that the value of target is less than $N$.</span></span>

<span data-ttu-id="a5232-120">V diagramu okruhu a vysvětlení, viz obrázek 5 na [stránce 5 arXiv: quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span><span class="sxs-lookup"><span data-stu-id="a5232-120">For the circuit diagram and explanation see Figure 5 on [Page 5 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span></span>

## <a name="see-also"></a><span data-ttu-id="a5232-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="a5232-121">See Also</span></span>

- [<span data-ttu-id="a5232-122">Microsoft. prostředníky. aritmetické. IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="a5232-122">Microsoft.Quantum.Arithmetic.IncrementByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)