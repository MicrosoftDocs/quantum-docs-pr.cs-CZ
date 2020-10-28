---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Operace ComputeReciprocalFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: e8f31d82fc69a3d7f4b571c4a679255dffc28b7f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707361"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="81306-102">Operace ComputeReciprocalFxP</span><span class="sxs-lookup"><span data-stu-id="81306-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="81306-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="81306-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="81306-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81306-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81306-105">Vypočítá $1/x $ pro číslo s pevnou desetinnou čárkou $x $.</span><span class="sxs-lookup"><span data-stu-id="81306-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="81306-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="81306-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="81306-107">x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="81306-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="81306-108">Číslo s pevnou desetinnou čárkou, které se má vrátit</span><span class="sxs-lookup"><span data-stu-id="81306-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="81306-109">výsledek: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="81306-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="81306-110">Číslo s pevnou desetinnou čárkou, které bude obsahovat výsledek.</span><span class="sxs-lookup"><span data-stu-id="81306-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="81306-111">Je nutné inicializovat na $ \ket{0.0} $.</span><span class="sxs-lookup"><span data-stu-id="81306-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81306-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81306-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

