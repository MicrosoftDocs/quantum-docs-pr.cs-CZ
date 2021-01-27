---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833304"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="f736b-102">IntAsBoolArray – funkce</span><span class="sxs-lookup"><span data-stu-id="f736b-102">IntAsBoolArray function</span></span>

<span data-ttu-id="f736b-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="f736b-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="f736b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f736b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f736b-105">Vytvoří binární reprezentaci nezáporného čísla s použitím reprezentace Little-endian pro vrácené pole.</span><span class="sxs-lookup"><span data-stu-id="f736b-105">Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="f736b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f736b-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="f736b-107">číslo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f736b-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f736b-108">Nezáporné celé číslo, které má být převedeno na pole logických hodnot.</span><span class="sxs-lookup"><span data-stu-id="f736b-108">A non-negative integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="f736b-109">bity: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f736b-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f736b-110">Počet bitů v binárním vyjádření `number` .</span><span class="sxs-lookup"><span data-stu-id="f736b-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f736b-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="f736b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="f736b-112">Pole logických hodnot, které představují `number` .</span><span class="sxs-lookup"><span data-stu-id="f736b-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f736b-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f736b-113">Remarks</span></span>

<span data-ttu-id="f736b-114">Vstup `bits` musí být v rozmezí od 0 do 63.</span><span class="sxs-lookup"><span data-stu-id="f736b-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="f736b-115">Vstup `number` musí být mezi 0 a $2 ^ {\texttt{BITS}}-$1.</span><span class="sxs-lookup"><span data-stu-id="f736b-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>