---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: Operace EvaluateEvenPolynomialFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: c3129cb796a344f7ad38a585183db285d48892bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843236"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="adf56-102">Operace EvaluateEvenPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="adf56-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="adf56-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="adf56-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="adf56-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="adf56-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="adf56-105">Vyhodnotí ještě polynomu v reprezentaci s pevnou desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="adf56-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="adf56-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="adf56-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="adf56-107">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="adf56-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="adf56-108">Koeficienty rovnoměrného polynomu jako dvojitá Array, tj. Array $ [a_0, a_1,..., a_k] $ pro ještě polynomická $P (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2k} $.</span><span class="sxs-lookup"><span data-stu-id="adf56-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="adf56-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="adf56-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="adf56-110">Vstupní číslo s pevnou desetinnou čárkou, pro které se má vyhodnotit polynomická hodnota</span><span class="sxs-lookup"><span data-stu-id="adf56-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="adf56-111">výsledek: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="adf56-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="adf56-112">Výstupní číslo s pevnou desetinnou čárkou, které bude obsahovat $P (x) $.</span><span class="sxs-lookup"><span data-stu-id="adf56-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="adf56-113">Musí být ve stavu $ \ket {0} $ původně.</span><span class="sxs-lookup"><span data-stu-id="adf56-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="adf56-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="adf56-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

