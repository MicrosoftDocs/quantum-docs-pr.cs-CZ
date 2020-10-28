---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: Operace MultiplyAndAddByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 3f85f6aaea1d6f8095709c6f387322df7a5e047c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706401"
---
# <a name="multiplyandaddbymodularinteger-operation"></a><span data-ttu-id="e35f8-102">Operace MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="e35f8-102">MultiplyAndAddByModularInteger operation</span></span>

<span data-ttu-id="e35f8-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e35f8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e35f8-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e35f8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e35f8-105">Provede modulární násobení a přidání celočíselnými konstantami v qubit registru.</span><span class="sxs-lookup"><span data-stu-id="e35f8-105">Performs a modular multiply-and-add by integer constants on a qubit register.</span></span>

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="e35f8-106">Popis</span><span class="sxs-lookup"><span data-stu-id="e35f8-106">Description</span></span>

<span data-ttu-id="e35f8-107">Implementuje mapu $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $ $ pro dané zbytky $N $, konstantní násobitel $a $ a summand $y $.</span><span class="sxs-lookup"><span data-stu-id="e35f8-107">Implements the map $$ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $$ for a given modulus $N$, constant multiplier $a$, and summand $y$.</span></span>

## <a name="input"></a><span data-ttu-id="e35f8-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="e35f8-108">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="e35f8-109">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e35f8-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e35f8-110">Do popisku každého základního stavu se přidá celé číslo $a $.</span><span class="sxs-lookup"><span data-stu-id="e35f8-110">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="e35f8-111">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e35f8-111">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e35f8-112">Zbytky $N $, které přidávají a násobení, se provádí s ohledem na.</span><span class="sxs-lookup"><span data-stu-id="e35f8-112">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="e35f8-113">násobitel: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e35f8-113">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e35f8-114">Registr v bajtech představuje unsigned integer, jehož hodnota má být přidána do každého popisku stavu `summand` .</span><span class="sxs-lookup"><span data-stu-id="e35f8-114">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="summand--littleendian"></a><span data-ttu-id="e35f8-115">summand: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e35f8-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e35f8-116">Registr nečinnosti, který představuje unsigned integer, který se má použít jako cíl pro tuto operaci.</span><span class="sxs-lookup"><span data-stu-id="e35f8-116">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e35f8-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e35f8-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e35f8-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e35f8-118">Remarks</span></span>

- <span data-ttu-id="e35f8-119">Pro diagram okruhu a vysvětlení, viz obrázek 6 na [stránce 7 arXiv: quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span><span class="sxs-lookup"><span data-stu-id="e35f8-119">For the circuit diagram and explanation see Figure 6 on [Page 7 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span></span>
- <span data-ttu-id="e35f8-120">Tato operace odpovídá funkci CMULT (a) MOD (N) v [arXiv: quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="e35f8-120">This operation corresponds to CMULT(a)MOD(N) in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>

## <a name="see-also"></a><span data-ttu-id="e35f8-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="e35f8-121">See Also</span></span>

- [<span data-ttu-id="e35f8-122">Microsoft. prostředníky. aritmetické. MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="e35f8-122">Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)