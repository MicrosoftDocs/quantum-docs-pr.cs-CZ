---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: Operace EvaluateOddPolynomialFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 852e986cd09c3b2e31263f53e381d9da73298415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846667"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="38090-102">Operace EvaluateOddPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="38090-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="38090-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="38090-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="38090-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="38090-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="38090-105">Vyhodnotí lichý polynom v reprezentaci s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="38090-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="38090-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="38090-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="38090-107">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="38090-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="38090-108">Poměrná část s lichým polynomem jako dvojitá Array, tj. Array $ [a_0, a_1,..., a_k] $ pro liché polynomy $P (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k × ^ {2k + 1} $.</span><span class="sxs-lookup"><span data-stu-id="38090-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="38090-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="38090-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="38090-110">Vstupní číslo s pevnou desetinnou čárkou, pro které se má vyhodnotit polynomická hodnota</span><span class="sxs-lookup"><span data-stu-id="38090-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="38090-111">výsledek: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="38090-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="38090-112">Výstupní číslo s pevnou desetinnou čárkou, které bude obsahovat P (x).</span><span class="sxs-lookup"><span data-stu-id="38090-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="38090-113">Musí být ve stavu $ \ket {0} $ původně.</span><span class="sxs-lookup"><span data-stu-id="38090-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="38090-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="38090-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

