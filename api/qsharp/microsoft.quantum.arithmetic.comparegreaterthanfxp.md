---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Operace CompareGreaterThanFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: bd3bcedd7a4a81fc600f7f4b6bdf1d2a797abbd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707393"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="c32e3-102">Operace CompareGreaterThanFxP</span><span class="sxs-lookup"><span data-stu-id="c32e3-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="c32e3-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c32e3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c32e3-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c32e3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c32e3-105">Porovná dvě číslo s pevnou desetinnou čárkou, která jsou uložená v registrech, a řídí převrácení výsledku.</span><span class="sxs-lookup"><span data-stu-id="c32e3-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="c32e3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c32e3-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="c32e3-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="c32e3-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="c32e3-108">První číslo s pevnou desetinnou čárkou, které se má porovnat</span><span class="sxs-lookup"><span data-stu-id="c32e3-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="c32e3-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="c32e3-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="c32e3-110">Druhé číslo s pevnou desetinnou čárkou, které se má porovnat</span><span class="sxs-lookup"><span data-stu-id="c32e3-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="c32e3-111">výsledek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c32e3-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c32e3-112">Výsledek porovnání</span><span class="sxs-lookup"><span data-stu-id="c32e3-112">Result of the comparison.</span></span> <span data-ttu-id="c32e3-113">Bude převráceno `fp1 > fp2` , pokud.</span><span class="sxs-lookup"><span data-stu-id="c32e3-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c32e3-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c32e3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c32e3-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c32e3-115">Remarks</span></span>

<span data-ttu-id="c32e3-116">Aktuální implementace vyžaduje, aby dvě čísla s pevnou desetinnou čárkou měla stejnou polohu bodu a stejný počet qubits.</span><span class="sxs-lookup"><span data-stu-id="c32e3-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>