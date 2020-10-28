---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707923"
---
# <a name="pnorm-function"></a><span data-ttu-id="07e07-102">PNorm – funkce</span><span class="sxs-lookup"><span data-stu-id="07e07-102">PNorm function</span></span>

<span data-ttu-id="07e07-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="07e07-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="07e07-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07e07-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07e07-105">Vrací `L(p)` normu vektoru `Double` s.</span><span class="sxs-lookup"><span data-stu-id="07e07-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="07e07-106">To znamená, že předané pole $x $ typu `Double[]` vrátí $p $-norm $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $.</span><span class="sxs-lookup"><span data-stu-id="07e07-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="07e07-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="07e07-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="07e07-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="07e07-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="07e07-109">Exponent $p $ v $p $-norma.</span><span class="sxs-lookup"><span data-stu-id="07e07-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="07e07-110">Array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="07e07-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="07e07-111">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="07e07-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="07e07-112">$P $-norm $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="07e07-112">The $p$-norm $\|x\|_p$.</span></span>