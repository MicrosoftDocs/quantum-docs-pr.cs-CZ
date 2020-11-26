---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: Operace EvaluateOddPolynomialFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 1bf9b6e7c416e994e70b93e5967caefd444f6426
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223217"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="65675-102">Operace EvaluateOddPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="65675-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="65675-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="65675-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="65675-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="65675-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="65675-105">Vyhodnotí lichý polynom v reprezentaci s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="65675-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="65675-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="65675-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="65675-107">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="65675-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="65675-108">Poměrná část s lichým polynomem jako dvojitá Array, tj. Array $ [a_0, a_1,..., a_k] $ pro liché polynomy $P (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k × ^ {2k + 1} $.</span><span class="sxs-lookup"><span data-stu-id="65675-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="65675-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="65675-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="65675-110">Vstupní číslo s pevnou desetinnou čárkou, pro které se má vyhodnotit polynomická hodnota</span><span class="sxs-lookup"><span data-stu-id="65675-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="65675-111">výsledek: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="65675-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="65675-112">Výstupní číslo s pevnou desetinnou čárkou, které bude obsahovat P (x).</span><span class="sxs-lookup"><span data-stu-id="65675-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="65675-113">Musí být ve stavu $ \ket {0} $ původně.</span><span class="sxs-lookup"><span data-stu-id="65675-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="65675-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65675-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

