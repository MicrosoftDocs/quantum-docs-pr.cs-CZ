---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Funkce diagonálního
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221534"
---
# <a name="diagonal-function"></a><span data-ttu-id="52505-102">Funkce diagonálního</span><span class="sxs-lookup"><span data-stu-id="52505-102">Diagonal function</span></span>

<span data-ttu-id="52505-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="52505-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="52505-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52505-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52505-105">Vrátí pole diagonálních elementů dvojrozměrného pole.</span><span class="sxs-lookup"><span data-stu-id="52505-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="52505-106">Popis</span><span class="sxs-lookup"><span data-stu-id="52505-106">Description</span></span>

<span data-ttu-id="52505-107">Pokud dvojrozměrné pole nemá čtvercový tvar, vrátí se hodnota příčně nad minimálním počtem řádků a sloupců.</span><span class="sxs-lookup"><span data-stu-id="52505-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="52505-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="52505-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="52505-109">matice: t [] []</span><span class="sxs-lookup"><span data-stu-id="52505-109">matrix : 'T[][]</span></span>

<span data-ttu-id="52505-110">dvojrozměrné matice v pořadí podle řádků</span><span class="sxs-lookup"><span data-stu-id="52505-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="52505-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="52505-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="52505-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="52505-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="52505-113">'S</span><span class="sxs-lookup"><span data-stu-id="52505-113">'T</span></span>

<span data-ttu-id="52505-114">Typ každého prvku `matrix` .</span><span class="sxs-lookup"><span data-stu-id="52505-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="52505-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="52505-115">See Also</span></span>

- [<span data-ttu-id="52505-116">Microsoft. prohození. Arrays. prohození</span><span class="sxs-lookup"><span data-stu-id="52505-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)