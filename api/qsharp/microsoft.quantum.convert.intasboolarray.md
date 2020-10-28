---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698289"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="d9d60-102">IntAsBoolArray – funkce</span><span class="sxs-lookup"><span data-stu-id="d9d60-102">IntAsBoolArray function</span></span>

<span data-ttu-id="d9d60-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="d9d60-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="d9d60-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9d60-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9d60-105">Vytvoří binární reprezentace kladného celého čísla s použitím reprezentace Little-endian pro vrácené pole.</span><span class="sxs-lookup"><span data-stu-id="d9d60-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="d9d60-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d9d60-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="d9d60-107">číslo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d9d60-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d9d60-108">Kladné celé číslo, které má být převedeno na pole logických hodnot.</span><span class="sxs-lookup"><span data-stu-id="d9d60-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="d9d60-109">bity: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d9d60-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d9d60-110">Počet bitů v binárním vyjádření `number` .</span><span class="sxs-lookup"><span data-stu-id="d9d60-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d9d60-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="d9d60-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="d9d60-112">Pole logických hodnot, které představují `number` .</span><span class="sxs-lookup"><span data-stu-id="d9d60-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9d60-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d9d60-113">Remarks</span></span>

<span data-ttu-id="d9d60-114">Vstup `bits` musí být v rozmezí od 0 do 63.</span><span class="sxs-lookup"><span data-stu-id="d9d60-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="d9d60-115">Vstup `number` musí být mezi 0 a $2 ^ {\texttt{BITS}}-$1.</span><span class="sxs-lookup"><span data-stu-id="d9d60-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>