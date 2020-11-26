---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Operace MultiplyFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 3c9ef9ade660e1f420d85162104d773b96722eeb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222605"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="440c4-102">Operace MultiplyFxP</span><span class="sxs-lookup"><span data-stu-id="440c4-102">MultiplyFxP operation</span></span>

<span data-ttu-id="440c4-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="440c4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="440c4-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="440c4-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="440c4-105">Vynásobí dvě čísla s pevnou desetinnou čárkou v registrech.</span><span class="sxs-lookup"><span data-stu-id="440c4-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="440c4-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="440c4-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="440c4-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="440c4-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="440c4-108">První číslo s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="440c4-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="440c4-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="440c4-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="440c4-110">Druhé číslo s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="440c4-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="440c4-111">výsledek: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="440c4-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="440c4-112">Výsledek s pevnou desetinnou čárkou, musí být ve stavu $ \ket {0} $ původně.</span><span class="sxs-lookup"><span data-stu-id="440c4-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="440c4-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="440c4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="440c4-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="440c4-114">Remarks</span></span>

<span data-ttu-id="440c4-115">Aktuální implementace vyžaduje, aby tři čísla s pevnou desetinnou čárkou měla stejnou polohu bodu a stejný počet qubits.</span><span class="sxs-lookup"><span data-stu-id="440c4-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>