---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Operace MultiplyFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 776ccb7a9e1ba1a34b28da6e1cf3a0aafe9da76b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843056"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="fb9d1-102">Operace MultiplyFxP</span><span class="sxs-lookup"><span data-stu-id="fb9d1-102">MultiplyFxP operation</span></span>

<span data-ttu-id="fb9d1-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fb9d1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fb9d1-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="fb9d1-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="fb9d1-105">Vynásobí dvě čísla s pevnou desetinnou čárkou v registrech.</span><span class="sxs-lookup"><span data-stu-id="fb9d1-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fb9d1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fb9d1-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="fb9d1-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="fb9d1-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="fb9d1-108">První číslo s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="fb9d1-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="fb9d1-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="fb9d1-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="fb9d1-110">Druhé číslo s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="fb9d1-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="fb9d1-111">výsledek: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="fb9d1-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="fb9d1-112">Výsledek s pevnou desetinnou čárkou, musí být ve stavu $ \ket {0} $ původně.</span><span class="sxs-lookup"><span data-stu-id="fb9d1-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fb9d1-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fb9d1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fb9d1-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fb9d1-114">Remarks</span></span>

<span data-ttu-id="fb9d1-115">Aktuální implementace vyžaduje, aby tři čísla s pevnou desetinnou čárkou měla stejnou polohu bodu a stejný počet qubits.</span><span class="sxs-lookup"><span data-stu-id="fb9d1-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>