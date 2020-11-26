---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227297"
---
# <a name="squarednorm-function"></a><span data-ttu-id="428c9-102">SquaredNorm – funkce</span><span class="sxs-lookup"><span data-stu-id="428c9-102">SquaredNorm function</span></span>

<span data-ttu-id="428c9-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="428c9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="428c9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="428c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="428c9-105">Vrátí čtvercovou 2-normu vektoru.</span><span class="sxs-lookup"><span data-stu-id="428c9-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="428c9-106">Popis</span><span class="sxs-lookup"><span data-stu-id="428c9-106">Description</span></span>

<span data-ttu-id="428c9-107">Vrátí čtvercovou 2-normu vektoru; To znamená, že zadané zadáním $ \vec{x} $ vrátí $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="428c9-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="428c9-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="428c9-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="428c9-109">Array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="428c9-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="428c9-110">Vektor, jehož čtvercová 2-norma se má vrátit.</span><span class="sxs-lookup"><span data-stu-id="428c9-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="428c9-111">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="428c9-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="428c9-112">Druhá 2 – norma `array` .</span><span class="sxs-lookup"><span data-stu-id="428c9-112">The squared 2-norm of `array`.</span></span>