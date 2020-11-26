---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Operace CompareGreaterThanFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: 1e9afc7645f62b932fa8ebc3d33e21a2a5182361
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223523"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="7d3ef-102">Operace CompareGreaterThanFxP</span><span class="sxs-lookup"><span data-stu-id="7d3ef-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="7d3ef-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7d3ef-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7d3ef-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="7d3ef-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="7d3ef-105">Porovná dvě číslo s pevnou desetinnou čárkou, která jsou uložená v registrech, a řídí převrácení výsledku.</span><span class="sxs-lookup"><span data-stu-id="7d3ef-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7d3ef-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7d3ef-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="7d3ef-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="7d3ef-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="7d3ef-108">První číslo s pevnou desetinnou čárkou, které se má porovnat</span><span class="sxs-lookup"><span data-stu-id="7d3ef-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="7d3ef-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="7d3ef-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="7d3ef-110">Druhé číslo s pevnou desetinnou čárkou, které se má porovnat</span><span class="sxs-lookup"><span data-stu-id="7d3ef-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="7d3ef-111">výsledek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7d3ef-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7d3ef-112">Výsledek porovnání</span><span class="sxs-lookup"><span data-stu-id="7d3ef-112">Result of the comparison.</span></span> <span data-ttu-id="7d3ef-113">Bude převráceno `fp1 > fp2` , pokud.</span><span class="sxs-lookup"><span data-stu-id="7d3ef-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d3ef-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d3ef-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7d3ef-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="7d3ef-115">Remarks</span></span>

<span data-ttu-id="7d3ef-116">Aktuální implementace vyžaduje, aby dvě čísla s pevnou desetinnou čárkou měla stejnou polohu bodu a stejný počet qubits.</span><span class="sxs-lookup"><span data-stu-id="7d3ef-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>