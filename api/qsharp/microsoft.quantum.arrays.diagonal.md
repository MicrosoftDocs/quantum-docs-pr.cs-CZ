---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Funkce diagonálního
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842830"
---
# <a name="diagonal-function"></a><span data-ttu-id="300eb-102">Funkce diagonálního</span><span class="sxs-lookup"><span data-stu-id="300eb-102">Diagonal function</span></span>

<span data-ttu-id="300eb-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="300eb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="300eb-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="300eb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="300eb-105">Vrátí pole diagonálních elementů dvojrozměrného pole.</span><span class="sxs-lookup"><span data-stu-id="300eb-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="300eb-106">Popis</span><span class="sxs-lookup"><span data-stu-id="300eb-106">Description</span></span>

<span data-ttu-id="300eb-107">Pokud dvojrozměrné pole nemá čtvercový tvar, vrátí se hodnota příčně nad minimálním počtem řádků a sloupců.</span><span class="sxs-lookup"><span data-stu-id="300eb-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="300eb-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="300eb-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="300eb-109">matice: t [] []</span><span class="sxs-lookup"><span data-stu-id="300eb-109">matrix : 'T[][]</span></span>

<span data-ttu-id="300eb-110">dvojrozměrné matice v pořadí podle řádků</span><span class="sxs-lookup"><span data-stu-id="300eb-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="300eb-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="300eb-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="300eb-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="300eb-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="300eb-113">'S</span><span class="sxs-lookup"><span data-stu-id="300eb-113">'T</span></span>

<span data-ttu-id="300eb-114">Typ každého prvku `matrix` .</span><span class="sxs-lookup"><span data-stu-id="300eb-114">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="300eb-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="300eb-115">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a><span data-ttu-id="300eb-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="300eb-116">See Also</span></span>

- [<span data-ttu-id="300eb-117">Microsoft. prohození. Arrays. prohození</span><span class="sxs-lookup"><span data-stu-id="300eb-117">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)