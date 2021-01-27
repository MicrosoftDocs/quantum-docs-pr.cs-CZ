---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846255"
---
# <a name="columnat-function"></a><span data-ttu-id="6d6ea-102">ColumnAt – funkce</span><span class="sxs-lookup"><span data-stu-id="6d6ea-102">ColumnAt function</span></span>

<span data-ttu-id="6d6ea-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6d6ea-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6d6ea-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6d6ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6d6ea-105">Extrahuje sloupec z matice.</span><span class="sxs-lookup"><span data-stu-id="6d6ea-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="6d6ea-106">Popis</span><span class="sxs-lookup"><span data-stu-id="6d6ea-106">Description</span></span>

<span data-ttu-id="6d6ea-107">Tato funkce extrahuje sloupec v matici v pořadí podle řádků.</span><span class="sxs-lookup"><span data-stu-id="6d6ea-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="6d6ea-108">Extrahování řádku corrsponds k přístupu k prvku prvního indexu, a proto nevyžaduje žádné další zpracování.</span><span class="sxs-lookup"><span data-stu-id="6d6ea-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="6d6ea-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="6d6ea-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="6d6ea-110">sloupec: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6d6ea-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6d6ea-111">Sloupec matice</span><span class="sxs-lookup"><span data-stu-id="6d6ea-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="6d6ea-112">matice: t [] []</span><span class="sxs-lookup"><span data-stu-id="6d6ea-112">matrix : 'T[][]</span></span>

<span data-ttu-id="6d6ea-113">dvojrozměrné matice v pořadí podle řádků</span><span class="sxs-lookup"><span data-stu-id="6d6ea-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="6d6ea-114">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="6d6ea-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6d6ea-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6d6ea-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6d6ea-116">'S</span><span class="sxs-lookup"><span data-stu-id="6d6ea-116">'T</span></span>

<span data-ttu-id="6d6ea-117">Typ každého prvku `matrix` .</span><span class="sxs-lookup"><span data-stu-id="6d6ea-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="6d6ea-118">Příklad</span><span class="sxs-lookup"><span data-stu-id="6d6ea-118">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a><span data-ttu-id="6d6ea-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="6d6ea-119">See Also</span></span>

- [<span data-ttu-id="6d6ea-120">Microsoft. prohození. Arrays. prohození</span><span class="sxs-lookup"><span data-stu-id="6d6ea-120">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="6d6ea-121">Microsoft. Forms. Arrays. diagonální</span><span class="sxs-lookup"><span data-stu-id="6d6ea-121">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)