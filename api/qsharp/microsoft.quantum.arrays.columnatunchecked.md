---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 17211c1ae1fe12fcadf34a9411f9b0cf0cdcab50
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706161"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="e50ac-102">ColumnAtUnchecked – funkce</span><span class="sxs-lookup"><span data-stu-id="e50ac-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="e50ac-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e50ac-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e50ac-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e50ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e50ac-105">Tato funkce nekontroluje tvar matice.</span><span class="sxs-lookup"><span data-stu-id="e50ac-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="e50ac-106">Popis</span><span class="sxs-lookup"><span data-stu-id="e50ac-106">Description</span></span>

<span data-ttu-id="e50ac-107">Tato funkce se dá použít v jiných multidimenzionálních funkcích, které už kontrolují vstupní matici platný obdélníkový tvar.</span><span class="sxs-lookup"><span data-stu-id="e50ac-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="e50ac-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="e50ac-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="e50ac-109">sloupec: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e50ac-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="e50ac-110">matice: t [] []</span><span class="sxs-lookup"><span data-stu-id="e50ac-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="e50ac-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="e50ac-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e50ac-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e50ac-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e50ac-113">'S</span><span class="sxs-lookup"><span data-stu-id="e50ac-113">'T</span></span>

