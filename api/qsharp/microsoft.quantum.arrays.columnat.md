---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210094"
---
# <a name="columnat-function"></a><span data-ttu-id="f9092-102">ColumnAt – funkce</span><span class="sxs-lookup"><span data-stu-id="f9092-102">ColumnAt function</span></span>

<span data-ttu-id="f9092-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f9092-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f9092-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9092-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9092-105">Extrahuje sloupec z matice.</span><span class="sxs-lookup"><span data-stu-id="f9092-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="f9092-106">Popis</span><span class="sxs-lookup"><span data-stu-id="f9092-106">Description</span></span>

<span data-ttu-id="f9092-107">Tato funkce extrahuje sloupec v matici v pořadí podle řádků.</span><span class="sxs-lookup"><span data-stu-id="f9092-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="f9092-108">Extrahování řádku corrsponds k přístupu k prvku prvního indexu, a proto nevyžaduje žádné další zpracování.</span><span class="sxs-lookup"><span data-stu-id="f9092-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="f9092-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="f9092-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="f9092-110">sloupec: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9092-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f9092-111">Sloupec matice</span><span class="sxs-lookup"><span data-stu-id="f9092-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="f9092-112">matice: t [] []</span><span class="sxs-lookup"><span data-stu-id="f9092-112">matrix : 'T[][]</span></span>

<span data-ttu-id="f9092-113">dvojrozměrné matice v pořadí podle řádků</span><span class="sxs-lookup"><span data-stu-id="f9092-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="f9092-114">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="f9092-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f9092-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f9092-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f9092-116">'S</span><span class="sxs-lookup"><span data-stu-id="f9092-116">'T</span></span>

<span data-ttu-id="f9092-117">Typ každého prvku `matrix` .</span><span class="sxs-lookup"><span data-stu-id="f9092-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9092-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="f9092-118">See Also</span></span>

- [<span data-ttu-id="f9092-119">Microsoft. prohození. Arrays. prohození</span><span class="sxs-lookup"><span data-stu-id="f9092-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="f9092-120">Microsoft. Forms. Arrays. diagonální</span><span class="sxs-lookup"><span data-stu-id="f9092-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)