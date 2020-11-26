---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 06fce23bbf7142ee0e0b0ed3f2c0578676f2097b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221585"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="be8a5-102">ColumnAtUnchecked – funkce</span><span class="sxs-lookup"><span data-stu-id="be8a5-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="be8a5-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="be8a5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="be8a5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="be8a5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="be8a5-105">Tato funkce nekontroluje tvar matice.</span><span class="sxs-lookup"><span data-stu-id="be8a5-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="be8a5-106">Popis</span><span class="sxs-lookup"><span data-stu-id="be8a5-106">Description</span></span>

<span data-ttu-id="be8a5-107">Tato funkce se dá použít v jiných multidimenzionálních funkcích, které už kontrolují vstupní matici platný obdélníkový tvar.</span><span class="sxs-lookup"><span data-stu-id="be8a5-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="be8a5-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="be8a5-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="be8a5-109">sloupec: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="be8a5-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="be8a5-110">matice: t [] []</span><span class="sxs-lookup"><span data-stu-id="be8a5-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="be8a5-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="be8a5-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="be8a5-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="be8a5-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="be8a5-113">'S</span><span class="sxs-lookup"><span data-stu-id="be8a5-113">'T</span></span>

