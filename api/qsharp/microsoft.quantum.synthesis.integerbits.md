---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706425"
---
# <a name="integerbits-function"></a><span data-ttu-id="91c56-102">IntegerBits – funkce</span><span class="sxs-lookup"><span data-stu-id="91c56-102">IntegerBits function</span></span>

<span data-ttu-id="91c56-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="91c56-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="91c56-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="91c56-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="91c56-105">Vrátí všechny pozice, ve kterých jsou nastaveny bity celého čísla.</span><span class="sxs-lookup"><span data-stu-id="91c56-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="91c56-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="91c56-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="91c56-107">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91c56-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="91c56-108">Nezáporné číslo.</span><span class="sxs-lookup"><span data-stu-id="91c56-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="91c56-109">Délka: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91c56-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="91c56-110">Počet bitů v binárním rozbalování `value` .</span><span class="sxs-lookup"><span data-stu-id="91c56-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="91c56-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="91c56-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="91c56-112">Pole obsahující všechny bitové pozice (počínaje 0), které jsou 1 v binárním rozšíření s `value` ohledem na všechny bity až do pozice `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="91c56-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="91c56-113">Všechny pozice jsou seřazené v poli podle pozice v rostoucím pořadí.</span><span class="sxs-lookup"><span data-stu-id="91c56-113">All positions are ordered in the array by position in an increasing order.</span></span>