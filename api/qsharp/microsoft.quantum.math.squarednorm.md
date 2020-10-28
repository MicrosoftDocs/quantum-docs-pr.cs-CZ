---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709088"
---
# <a name="squarednorm-function"></a><span data-ttu-id="ebde4-102">SquaredNorm – funkce</span><span class="sxs-lookup"><span data-stu-id="ebde4-102">SquaredNorm function</span></span>

<span data-ttu-id="ebde4-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ebde4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ebde4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ebde4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ebde4-105">Vrátí čtvercovou 2-normu vektoru.</span><span class="sxs-lookup"><span data-stu-id="ebde4-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="ebde4-106">Popis</span><span class="sxs-lookup"><span data-stu-id="ebde4-106">Description</span></span>

<span data-ttu-id="ebde4-107">Vrátí čtvercovou 2-normu vektoru; To znamená, že zadané zadáním $ \vec{x} $ vrátí $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="ebde4-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="ebde4-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="ebde4-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="ebde4-109">Array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ebde4-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ebde4-110">Vektor, jehož čtvercová 2-norma se má vrátit.</span><span class="sxs-lookup"><span data-stu-id="ebde4-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="ebde4-111">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ebde4-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ebde4-112">Druhá 2 – norma `array` .</span><span class="sxs-lookup"><span data-stu-id="ebde4-112">The squared 2-norm of `array`.</span></span>