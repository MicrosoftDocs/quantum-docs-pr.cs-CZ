---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: Operace AddFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 60b7cad3d0bd8800e67830ca921f8e2d705b8f39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843856"
---
# <a name="addfxp-operation"></a><span data-ttu-id="2807f-102">Operace AddFxP</span><span class="sxs-lookup"><span data-stu-id="2807f-102">AddFxP operation</span></span>

<span data-ttu-id="2807f-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2807f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2807f-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="2807f-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="2807f-105">Přidá dvě čísla s pevnou desetinnou čárkou uložená v registrech.</span><span class="sxs-lookup"><span data-stu-id="2807f-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2807f-106">Popis</span><span class="sxs-lookup"><span data-stu-id="2807f-106">Description</span></span>

<span data-ttu-id="2807f-107">V uvedeném pořadí se dvěma Registry s pevnou desetinnou čárkou ve stavech $ \ket{f_1} $ a $ \ket{f_2} $ provede operace $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $.</span><span class="sxs-lookup"><span data-stu-id="2807f-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="2807f-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="2807f-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="2807f-109">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="2807f-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="2807f-110">První číslo s pevnou desetinnou čárkou</span><span class="sxs-lookup"><span data-stu-id="2807f-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="2807f-111">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="2807f-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="2807f-112">Druhé číslo s pevnou desetinnou čárkou se aktualizuje tak, aby obsahovalo součet dvou vstupů.</span><span class="sxs-lookup"><span data-stu-id="2807f-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2807f-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2807f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2807f-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2807f-114">Remarks</span></span>

<span data-ttu-id="2807f-115">Aktuální implementace vyžaduje, aby dvě čísla s pevnou desetinnou čárkou byla počítána od nejméně významného bitu, tj. $n _i $ a $p _i $ musí být rovna.</span><span class="sxs-lookup"><span data-stu-id="2807f-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>