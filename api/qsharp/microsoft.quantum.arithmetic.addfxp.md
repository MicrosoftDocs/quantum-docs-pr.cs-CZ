---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: Operace AddFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707664"
---
# <a name="addfxp-operation"></a><span data-ttu-id="29291-102">Operace AddFxP</span><span class="sxs-lookup"><span data-stu-id="29291-102">AddFxP operation</span></span>

<span data-ttu-id="29291-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="29291-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="29291-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="29291-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="29291-105">Přidá dvě čísla s pevnou desetinnou čárkou uložená v registrech.</span><span class="sxs-lookup"><span data-stu-id="29291-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a><span data-ttu-id="29291-106">Popis</span><span class="sxs-lookup"><span data-stu-id="29291-106">Description</span></span>

<span data-ttu-id="29291-107">V uvedeném pořadí se dvěma Registry s pevnou desetinnou čárkou ve stavech $ \ket{f_1} $ a $ \ket{f_2} $ provede operace $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $.</span><span class="sxs-lookup"><span data-stu-id="29291-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="29291-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="29291-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="29291-109">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="29291-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="29291-110">První číslo s pevnou desetinnou čárkou</span><span class="sxs-lookup"><span data-stu-id="29291-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="29291-111">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="29291-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="29291-112">Druhé číslo s pevnou desetinnou čárkou se aktualizuje tak, aby obsahovalo součet dvou vstupů.</span><span class="sxs-lookup"><span data-stu-id="29291-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="29291-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="29291-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="29291-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="29291-114">Remarks</span></span>

<span data-ttu-id="29291-115">Aktuální implementace vyžaduje, aby dvě čísla s pevnou desetinnou čárkou byla počítána od nejméně významného bitu, tj. $n _i $ a $p _i $ musí být rovna.</span><span class="sxs-lookup"><span data-stu-id="29291-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>