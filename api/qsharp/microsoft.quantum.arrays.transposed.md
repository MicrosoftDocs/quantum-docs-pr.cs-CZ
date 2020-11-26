---
uid: Microsoft.Quantum.Arrays.Transposed
title: Funkce převzata
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: f293399d8e3a2cb32b2929e8d1591ac5eaefd277
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219987"
---
# <a name="transposed-function"></a><span data-ttu-id="a842a-102">Funkce převzata</span><span class="sxs-lookup"><span data-stu-id="a842a-102">Transposed function</span></span>

<span data-ttu-id="a842a-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a842a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a842a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a842a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a842a-105">Vrátí transpozice matice reprezentované jako pole polí.</span><span class="sxs-lookup"><span data-stu-id="a842a-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="a842a-106">Popis</span><span class="sxs-lookup"><span data-stu-id="a842a-106">Description</span></span>

<span data-ttu-id="a842a-107">Vstup jako $r \times c $ Matrix s $r $ Rows a $c $ Columns.</span><span class="sxs-lookup"><span data-stu-id="a842a-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="a842a-108">Matice je založena na řádcích, tj. `matrix[i][j]` přistupuje k elementu na řádku $i $ a sloupci $j $.</span><span class="sxs-lookup"><span data-stu-id="a842a-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="a842a-109">Tato funkce vrací matici $c \times r $, která je transpozice vstupní matice.</span><span class="sxs-lookup"><span data-stu-id="a842a-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="a842a-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="a842a-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="a842a-111">matice: t [] []</span><span class="sxs-lookup"><span data-stu-id="a842a-111">matrix : 'T[][]</span></span>

<span data-ttu-id="a842a-112">Matice $r \times založené na řádku jazyka c $</span><span class="sxs-lookup"><span data-stu-id="a842a-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="a842a-113">Výstup: t [] []</span><span class="sxs-lookup"><span data-stu-id="a842a-113">Output : 'T[][]</span></span>

<span data-ttu-id="a842a-114">$C \times r $ Matrix pro přeměňování</span><span class="sxs-lookup"><span data-stu-id="a842a-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a842a-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a842a-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a842a-116">'S</span><span class="sxs-lookup"><span data-stu-id="a842a-116">'T</span></span>

<span data-ttu-id="a842a-117">Typ každého prvku `matrix` .</span><span class="sxs-lookup"><span data-stu-id="a842a-117">The type of each element of `matrix`.</span></span>