---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855405"
---
# <a name="integerbits-function"></a><span data-ttu-id="e3377-102">IntegerBits – funkce</span><span class="sxs-lookup"><span data-stu-id="e3377-102">IntegerBits function</span></span>

<span data-ttu-id="e3377-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="e3377-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="e3377-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3377-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3377-105">Vrátí všechny pozice, ve kterých jsou nastaveny bity celého čísla.</span><span class="sxs-lookup"><span data-stu-id="e3377-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="e3377-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e3377-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="e3377-107">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e3377-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e3377-108">Nezáporné číslo.</span><span class="sxs-lookup"><span data-stu-id="e3377-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="e3377-109">Délka: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e3377-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e3377-110">Počet bitů v binárním rozbalování `value` .</span><span class="sxs-lookup"><span data-stu-id="e3377-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="e3377-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e3377-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e3377-112">Pole obsahující všechny bitové pozice (počínaje 0), které jsou 1 v binárním rozšíření s `value` ohledem na všechny bity až do pozice `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="e3377-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="e3377-113">Všechny pozice jsou seřazené v poli podle pozice v rostoucím pořadí.</span><span class="sxs-lookup"><span data-stu-id="e3377-113">All positions are ordered in the array by position in an increasing order.</span></span>

## <a name="example"></a><span data-ttu-id="e3377-114">Příklad</span><span class="sxs-lookup"><span data-stu-id="e3377-114">Example</span></span>

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```