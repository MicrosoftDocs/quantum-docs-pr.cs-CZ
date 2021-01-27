---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854839"
---
# <a name="pnormalized-function"></a><span data-ttu-id="1a216-102">PNormalized – funkce</span><span class="sxs-lookup"><span data-stu-id="1a216-102">PNormalized function</span></span>

<span data-ttu-id="1a216-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1a216-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1a216-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1a216-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1a216-105">Normalizuje vektor `Double` s v `L(p)` normě.</span><span class="sxs-lookup"><span data-stu-id="1a216-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="1a216-106">To znamená, že předané pole $x $ typu `Double[]` vrátí pole, kde jsou všechny prvky děleny $p $-norm $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="1a216-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="1a216-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="1a216-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="1a216-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1a216-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1a216-109">Exponent $p $ v $p $-norma.</span><span class="sxs-lookup"><span data-stu-id="1a216-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="1a216-110">Array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="1a216-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="1a216-111">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="1a216-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="1a216-112">Pole $x $ normalizován $p $-norm $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="1a216-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a216-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="1a216-113">See Also</span></span>

- [<span data-ttu-id="1a216-114">Microsoft. PNorm. Math.</span><span class="sxs-lookup"><span data-stu-id="1a216-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)