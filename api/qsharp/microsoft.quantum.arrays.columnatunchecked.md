---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 4f4631bb49f769816a3df772f7b2f346c8ccfc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842867"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="c660d-102">ColumnAtUnchecked – funkce</span><span class="sxs-lookup"><span data-stu-id="c660d-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="c660d-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c660d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c660d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c660d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c660d-105">Tato funkce nekontroluje tvar matice.</span><span class="sxs-lookup"><span data-stu-id="c660d-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="c660d-106">Popis</span><span class="sxs-lookup"><span data-stu-id="c660d-106">Description</span></span>

<span data-ttu-id="c660d-107">Tato funkce se dá použít v jiných multidimenzionálních funkcích, které už kontrolují vstupní matici platný obdélníkový tvar.</span><span class="sxs-lookup"><span data-stu-id="c660d-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="c660d-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="c660d-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="c660d-109">sloupec: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c660d-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="c660d-110">matice: t [] []</span><span class="sxs-lookup"><span data-stu-id="c660d-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="c660d-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="c660d-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c660d-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c660d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c660d-113">'S</span><span class="sxs-lookup"><span data-stu-id="c660d-113">'T</span></span>

