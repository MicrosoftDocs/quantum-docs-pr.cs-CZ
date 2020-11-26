---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: Operace EvaluateEvenPolynomialFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: 21c700ccb2b87b906fc4d8b65eddf962353948c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223251"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="7e4ed-102">Operace EvaluateEvenPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="7e4ed-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="7e4ed-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7e4ed-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7e4ed-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="7e4ed-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="7e4ed-105">Vyhodnotí ještě polynomu v reprezentaci s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7e4ed-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7e4ed-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="7e4ed-107">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7e4ed-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7e4ed-108">Koeficienty rovnoměrného polynomu jako dvojitá Array, tj. Array $ [a_0, a_1,..., a_k] $ pro ještě polynomická $P (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2k} $.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="7e4ed-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="7e4ed-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="7e4ed-110">Vstupní číslo s pevnou desetinnou čárkou, pro které se má vyhodnotit polynomická hodnota</span><span class="sxs-lookup"><span data-stu-id="7e4ed-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="7e4ed-111">výsledek: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="7e4ed-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="7e4ed-112">Výstupní číslo s pevnou desetinnou čárkou, které bude obsahovat $P (x) $.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="7e4ed-113">Musí být ve stavu $ \ket {0} $ původně.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7e4ed-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e4ed-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

