---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Operace ComputeReciprocalFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: 3ca050d6ce9daaa10e14c2f12dd571398cf436b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223387"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="0d8a0-102">Operace ComputeReciprocalFxP</span><span class="sxs-lookup"><span data-stu-id="0d8a0-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="0d8a0-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0d8a0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0d8a0-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="0d8a0-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="0d8a0-105">Vypočítá $1/x $ pro číslo s pevnou desetinnou čárkou $x $.</span><span class="sxs-lookup"><span data-stu-id="0d8a0-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0d8a0-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="0d8a0-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="0d8a0-107">x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="0d8a0-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="0d8a0-108">Číslo s pevnou desetinnou čárkou, které se má vrátit</span><span class="sxs-lookup"><span data-stu-id="0d8a0-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="0d8a0-109">výsledek: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="0d8a0-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="0d8a0-110">Číslo s pevnou desetinnou čárkou, které bude obsahovat výsledek.</span><span class="sxs-lookup"><span data-stu-id="0d8a0-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="0d8a0-111">Je nutné inicializovat na $ \ket{0.0} $.</span><span class="sxs-lookup"><span data-stu-id="0d8a0-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0d8a0-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d8a0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

