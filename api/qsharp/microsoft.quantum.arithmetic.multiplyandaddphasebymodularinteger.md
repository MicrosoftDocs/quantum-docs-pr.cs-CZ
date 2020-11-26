---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Operace MultiplyAndAddPhaseByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: 1ca20b525d2a76e554d5a2e8d4f40060b5ef51cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223863"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="3e83b-102">Operace MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="3e83b-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="3e83b-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3e83b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3e83b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3e83b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3e83b-105">Stejné jako MultiplyAndAddByModularInteger, ale předpokládá, že summand kóduje celá čísla v QFT základ.</span><span class="sxs-lookup"><span data-stu-id="3e83b-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3e83b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3e83b-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="3e83b-107">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3e83b-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3e83b-108">Do popisku každého základního stavu se přidá celé číslo $a $.</span><span class="sxs-lookup"><span data-stu-id="3e83b-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="3e83b-109">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3e83b-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3e83b-110">Zbytky $N $, které přidávají a násobení, se provádí s ohledem na.</span><span class="sxs-lookup"><span data-stu-id="3e83b-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="3e83b-111">násobitel: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3e83b-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3e83b-112">Registr v bajtech představuje unsigned integer, jehož hodnota má být přidána do každého popisku stavu `summand` .</span><span class="sxs-lookup"><span data-stu-id="3e83b-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="3e83b-113">phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3e83b-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="3e83b-114">Registr nečinnosti, který představuje unsigned integer, který se má použít jako cíl pro tuto operaci.</span><span class="sxs-lookup"><span data-stu-id="3e83b-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e83b-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e83b-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3e83b-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3e83b-116">Remarks</span></span>

<span data-ttu-id="3e83b-117">Předpokládá, že `phaseSummand` má nejvyšší bit nastavený na hodnotu 0.</span><span class="sxs-lookup"><span data-stu-id="3e83b-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="3e83b-118">Také předpokládá, že hodnota `phaseSummand` je menší než $N $.</span><span class="sxs-lookup"><span data-stu-id="3e83b-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e83b-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="3e83b-119">See Also</span></span>

- [<span data-ttu-id="3e83b-120">Microsoft. prostředníky. aritmetické. MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="3e83b-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)