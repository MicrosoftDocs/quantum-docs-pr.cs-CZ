---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706168"
---
# <a name="columnat-function"></a><span data-ttu-id="25c25-102">ColumnAt – funkce</span><span class="sxs-lookup"><span data-stu-id="25c25-102">ColumnAt function</span></span>

<span data-ttu-id="25c25-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="25c25-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="25c25-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25c25-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25c25-105">Extrahuje sloupec z matice.</span><span class="sxs-lookup"><span data-stu-id="25c25-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="25c25-106">Popis</span><span class="sxs-lookup"><span data-stu-id="25c25-106">Description</span></span>

<span data-ttu-id="25c25-107">Tato funkce extrahuje sloupec v matici v pořadí podle řádků.</span><span class="sxs-lookup"><span data-stu-id="25c25-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="25c25-108">Extrahování řádku corrsponds k přístupu k prvku prvního indexu, a proto nevyžaduje žádné další zpracování.</span><span class="sxs-lookup"><span data-stu-id="25c25-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="25c25-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="25c25-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="25c25-110">sloupec: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25c25-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="25c25-111">Sloupec matice</span><span class="sxs-lookup"><span data-stu-id="25c25-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="25c25-112">matice: t [] []</span><span class="sxs-lookup"><span data-stu-id="25c25-112">matrix : 'T[][]</span></span>

<span data-ttu-id="25c25-113">dvojrozměrné matice v pořadí podle řádků</span><span class="sxs-lookup"><span data-stu-id="25c25-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="25c25-114">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="25c25-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="25c25-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="25c25-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="25c25-116">'S</span><span class="sxs-lookup"><span data-stu-id="25c25-116">'T</span></span>

<span data-ttu-id="25c25-117">Typ každého prvku `matrix` .</span><span class="sxs-lookup"><span data-stu-id="25c25-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="25c25-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="25c25-118">See Also</span></span>

- [<span data-ttu-id="25c25-119">Microsoft. prohození. Arrays. prohození</span><span class="sxs-lookup"><span data-stu-id="25c25-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="25c25-120">Microsoft. Forms. Arrays. diagonální</span><span class="sxs-lookup"><span data-stu-id="25c25-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)