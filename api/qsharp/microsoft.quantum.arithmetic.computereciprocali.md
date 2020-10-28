---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: Operace ComputeReciprocalI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: b99e816ed69af6e6d1758442d6f95c5ab0e5c07a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707345"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="936bb-102">Operace ComputeReciprocalI</span><span class="sxs-lookup"><span data-stu-id="936bb-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="936bb-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="936bb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="936bb-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="936bb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="936bb-105">Vypočítá protější hodnotu 1/x pro unsigned integer x pomocí dělení celého čísla.</span><span class="sxs-lookup"><span data-stu-id="936bb-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="936bb-106">Výsledek, který je interpretován jako celé číslo, bude `floor(2^(2*n-1) / x)` .</span><span class="sxs-lookup"><span data-stu-id="936bb-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="936bb-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="936bb-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="936bb-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="936bb-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="936bb-109">n-bit unsigned integer</span><span class="sxs-lookup"><span data-stu-id="936bb-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="936bb-110">výsledek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="936bb-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="936bb-111">2N výstup musí být zpočátku v $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="936bb-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="936bb-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="936bb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="936bb-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="936bb-113">Remarks</span></span>

<span data-ttu-id="936bb-114">U vstupu x = 0 bude výstup všech.</span><span class="sxs-lookup"><span data-stu-id="936bb-114">For the input x=0, the output will be all-ones.</span></span>