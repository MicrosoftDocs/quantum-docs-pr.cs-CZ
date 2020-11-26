---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: Operace ComputeReciprocalI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: 9024da4a457265c65a41ef681cfbb99ebd4989a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223353"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="4fe82-102">Operace ComputeReciprocalI</span><span class="sxs-lookup"><span data-stu-id="4fe82-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="4fe82-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4fe82-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4fe82-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="4fe82-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="4fe82-105">Vypočítá protější hodnotu 1/x pro unsigned integer x pomocí dělení celého čísla.</span><span class="sxs-lookup"><span data-stu-id="4fe82-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="4fe82-106">Výsledek, který je interpretován jako celé číslo, bude `floor(2^(2*n-1) / x)` .</span><span class="sxs-lookup"><span data-stu-id="4fe82-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4fe82-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="4fe82-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="4fe82-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4fe82-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4fe82-109">n-bit unsigned integer</span><span class="sxs-lookup"><span data-stu-id="4fe82-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="4fe82-110">výsledek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4fe82-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4fe82-111">2N výstup musí být zpočátku v $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="4fe82-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4fe82-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4fe82-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4fe82-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4fe82-113">Remarks</span></span>

<span data-ttu-id="4fe82-114">U vstupu x = 0 bude výstup všech.</span><span class="sxs-lookup"><span data-stu-id="4fe82-114">For the input x=0, the output will be all-ones.</span></span>