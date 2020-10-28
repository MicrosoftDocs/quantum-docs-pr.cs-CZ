---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: Operace IncrementPhaseByInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fb67455dadbc7a2f38880581f0e413a747faa8ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707248"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="dcb58-102">Operace IncrementPhaseByInteger</span><span class="sxs-lookup"><span data-stu-id="dcb58-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="dcb58-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="dcb58-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="dcb58-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dcb58-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dcb58-105">Zvýší nepodepsaná bezplatných hodnot do registru pomocí klasického celého čísla pomocí otočení fáze.</span><span class="sxs-lookup"><span data-stu-id="dcb58-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="dcb58-106">Popis</span><span class="sxs-lookup"><span data-stu-id="dcb58-106">Description</span></span>

<span data-ttu-id="dcb58-107">Předpokládejme, že `target` kódování unsigned integer $x $ v kódování Little endian a `increment` je rovno $a $.</span><span class="sxs-lookup"><span data-stu-id="dcb58-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="dcb58-108">Tato operace pak implementuje jednotkové $ \ket{x} \mapsto \ket{x + a} $, kde sčítání se provádí modulo $2 ^ n $, kde $n = \texttt{Length (Target!)} $.</span><span class="sxs-lookup"><span data-stu-id="dcb58-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="dcb58-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="dcb58-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="dcb58-110">přírůstek: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dcb58-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dcb58-111">Celé číslo, kterým `target` se zvyšuje hodnota.</span><span class="sxs-lookup"><span data-stu-id="dcb58-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="dcb58-112">cíl: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dcb58-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="dcb58-113">V poli pro duální (QFT) se registruje při kódování nenáročného využívání unsigned integer.</span><span class="sxs-lookup"><span data-stu-id="dcb58-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dcb58-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dcb58-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dcb58-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="dcb58-115">Remarks</span></span>

<span data-ttu-id="dcb58-116">Všimněte si, že jsme tento okruh zjednodušili, protože přírůstek je klasická konstanta, ne Pokladna za sebou.</span><span class="sxs-lookup"><span data-stu-id="dcb58-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="dcb58-117">Podívejte se na obrázek na [ stránce 6 arXiv: quant-pH/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) pro diagram okruhu a vysvětlení.</span><span class="sxs-lookup"><span data-stu-id="dcb58-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="dcb58-118">Odkazy</span><span class="sxs-lookup"><span data-stu-id="dcb58-118">References</span></span>

- [<span data-ttu-id="dcb58-119">*Tomáš G. Draper* , arXiv: quant-pH/0008033</span><span class="sxs-lookup"><span data-stu-id="dcb58-119"> *Thomas G. Draper* , arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="dcb58-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="dcb58-120">See Also</span></span>

- [<span data-ttu-id="dcb58-121">Microsoft. prostředníky. aritmetické. IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="dcb58-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)