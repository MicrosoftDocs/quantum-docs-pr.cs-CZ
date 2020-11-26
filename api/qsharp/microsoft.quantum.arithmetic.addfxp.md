---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: Operace AddFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 36a5d585a493f0e6f33f74b1686aaa01cca7ac0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191036"
---
# <a name="addfxp-operation"></a><span data-ttu-id="85b40-102">Operace AddFxP</span><span class="sxs-lookup"><span data-stu-id="85b40-102">AddFxP operation</span></span>

<span data-ttu-id="85b40-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="85b40-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="85b40-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="85b40-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="85b40-105">Přidá dvě čísla s pevnou desetinnou čárkou uložená v registrech.</span><span class="sxs-lookup"><span data-stu-id="85b40-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="85b40-106">Popis</span><span class="sxs-lookup"><span data-stu-id="85b40-106">Description</span></span>

<span data-ttu-id="85b40-107">V uvedeném pořadí se dvěma Registry s pevnou desetinnou čárkou ve stavech $ \ket{f_1} $ a $ \ket{f_2} $ provede operace $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $.</span><span class="sxs-lookup"><span data-stu-id="85b40-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="85b40-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="85b40-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="85b40-109">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="85b40-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="85b40-110">První číslo s pevnou desetinnou čárkou</span><span class="sxs-lookup"><span data-stu-id="85b40-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="85b40-111">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="85b40-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="85b40-112">Druhé číslo s pevnou desetinnou čárkou se aktualizuje tak, aby obsahovalo součet dvou vstupů.</span><span class="sxs-lookup"><span data-stu-id="85b40-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="85b40-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="85b40-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="85b40-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="85b40-114">Remarks</span></span>

<span data-ttu-id="85b40-115">Aktuální implementace vyžaduje, aby dvě čísla s pevnou desetinnou čárkou byla počítána od nejméně významného bitu, tj. $n _i $ a $p _i $ musí být rovna.</span><span class="sxs-lookup"><span data-stu-id="85b40-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>