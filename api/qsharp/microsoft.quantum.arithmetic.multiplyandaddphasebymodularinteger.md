---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Operace MultiplyAndAddPhaseByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: b1214acc2cafc3fede9fcb6663a435c0b1d2cf4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843061"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="ac46a-102">Operace MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="ac46a-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="ac46a-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ac46a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ac46a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac46a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac46a-105">Stejné jako MultiplyAndAddByModularInteger, ale předpokládá, že summand kóduje celá čísla v QFT základ.</span><span class="sxs-lookup"><span data-stu-id="ac46a-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ac46a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ac46a-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="ac46a-107">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac46a-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac46a-108">Do popisku každého základního stavu se přidá celé číslo $a $.</span><span class="sxs-lookup"><span data-stu-id="ac46a-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="ac46a-109">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac46a-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac46a-110">Zbytky $N $, které přidávají a násobení, se provádí s ohledem na.</span><span class="sxs-lookup"><span data-stu-id="ac46a-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="ac46a-111">násobitel: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ac46a-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ac46a-112">Registr v bajtech představuje unsigned integer, jehož hodnota má být přidána do každého popisku stavu `summand` .</span><span class="sxs-lookup"><span data-stu-id="ac46a-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="ac46a-113">phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ac46a-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="ac46a-114">Registr nečinnosti, který představuje unsigned integer, který se má použít jako cíl pro tuto operaci.</span><span class="sxs-lookup"><span data-stu-id="ac46a-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ac46a-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac46a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ac46a-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ac46a-116">Remarks</span></span>

<span data-ttu-id="ac46a-117">Předpokládá, že `phaseSummand` má nejvyšší bit nastavený na hodnotu 0.</span><span class="sxs-lookup"><span data-stu-id="ac46a-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="ac46a-118">Také předpokládá, že hodnota `phaseSummand` je menší než $N $.</span><span class="sxs-lookup"><span data-stu-id="ac46a-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac46a-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="ac46a-119">See Also</span></span>

- [<span data-ttu-id="ac46a-120">Microsoft. prostředníky. aritmetické. MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="ac46a-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)