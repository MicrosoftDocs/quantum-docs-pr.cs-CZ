---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 196bdab67528aa8672a010ac3830459e27276ce9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227518"
---
# <a name="pnormalized-function"></a><span data-ttu-id="f4d53-102">PNormalized – funkce</span><span class="sxs-lookup"><span data-stu-id="f4d53-102">PNormalized function</span></span>

<span data-ttu-id="f4d53-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f4d53-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f4d53-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4d53-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4d53-105">Normalizuje vektor `Double` s v `L(p)` normě.</span><span class="sxs-lookup"><span data-stu-id="f4d53-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="f4d53-106">To znamená, že předané pole $x $ typu `Double[]` vrátí pole, kde jsou všechny prvky děleny $p $-norm $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="f4d53-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="f4d53-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="f4d53-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="f4d53-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4d53-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f4d53-109">Exponent $p $ v $p $-norma.</span><span class="sxs-lookup"><span data-stu-id="f4d53-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="f4d53-110">Array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f4d53-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="f4d53-111">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f4d53-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f4d53-112">Pole $x $ normalizován $p $-norm $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="f4d53-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4d53-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="f4d53-113">See Also</span></span>

- [<span data-ttu-id="f4d53-114">Microsoft. PNorm. Math.</span><span class="sxs-lookup"><span data-stu-id="f4d53-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)