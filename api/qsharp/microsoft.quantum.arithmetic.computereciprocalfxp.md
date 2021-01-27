---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Operace ComputeReciprocalFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: db7425f1a8a9b5ddfdc6b123dad003298e3670e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843249"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="3647e-102">Operace ComputeReciprocalFxP</span><span class="sxs-lookup"><span data-stu-id="3647e-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="3647e-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3647e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3647e-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="3647e-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="3647e-105">Vypočítá $1/x $ pro číslo s pevnou desetinnou čárkou $x $.</span><span class="sxs-lookup"><span data-stu-id="3647e-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3647e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3647e-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="3647e-107">x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="3647e-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="3647e-108">Číslo s pevnou desetinnou čárkou, které se má vrátit</span><span class="sxs-lookup"><span data-stu-id="3647e-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="3647e-109">výsledek: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="3647e-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="3647e-110">Číslo s pevnou desetinnou čárkou, které bude obsahovat výsledek.</span><span class="sxs-lookup"><span data-stu-id="3647e-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="3647e-111">Je nutné inicializovat na $ \ket{0.0} $.</span><span class="sxs-lookup"><span data-stu-id="3647e-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3647e-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3647e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

