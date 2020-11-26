---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: f89cb3d7ca29d7deaaf49573b2670534166caded
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224339"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="b3226-102">IntAsBoolArray – funkce</span><span class="sxs-lookup"><span data-stu-id="b3226-102">IntAsBoolArray function</span></span>

<span data-ttu-id="b3226-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="b3226-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="b3226-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b3226-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b3226-105">Vytvoří binární reprezentace kladného celého čísla s použitím reprezentace Little-endian pro vrácené pole.</span><span class="sxs-lookup"><span data-stu-id="b3226-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="b3226-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b3226-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="b3226-107">číslo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b3226-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b3226-108">Kladné celé číslo, které má být převedeno na pole logických hodnot.</span><span class="sxs-lookup"><span data-stu-id="b3226-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="b3226-109">bity: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b3226-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b3226-110">Počet bitů v binárním vyjádření `number` .</span><span class="sxs-lookup"><span data-stu-id="b3226-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b3226-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b3226-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b3226-112">Pole logických hodnot, které představují `number` .</span><span class="sxs-lookup"><span data-stu-id="b3226-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b3226-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b3226-113">Remarks</span></span>

<span data-ttu-id="b3226-114">Vstup `bits` musí být v rozmezí od 0 do 63.</span><span class="sxs-lookup"><span data-stu-id="b3226-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="b3226-115">Vstup `number` musí být mezi 0 a $2 ^ {\texttt{BITS}}-$1.</span><span class="sxs-lookup"><span data-stu-id="b3226-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>