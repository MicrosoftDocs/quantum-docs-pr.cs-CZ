---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705961"
---
# <a name="indexrange-function"></a><span data-ttu-id="45afe-102">IndexRange – funkce</span><span class="sxs-lookup"><span data-stu-id="45afe-102">IndexRange function</span></span>

<span data-ttu-id="45afe-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="45afe-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="45afe-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45afe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45afe-105">V poli, vrátí rozsah v rámci indexů tohoto pole, který je vhodný pro použití ve smyčce for.</span><span class="sxs-lookup"><span data-stu-id="45afe-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="45afe-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="45afe-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="45afe-107">Array: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="45afe-107">array : 'TElement[]</span></span>

<span data-ttu-id="45afe-108">Pole, pro které by měl být vrácen rozsah indexů.</span><span class="sxs-lookup"><span data-stu-id="45afe-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="45afe-109">Výstup: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="45afe-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="45afe-110">Rozsah ve všech indexech pole.</span><span class="sxs-lookup"><span data-stu-id="45afe-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="45afe-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="45afe-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="45afe-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="45afe-112">'TElement</span></span>

<span data-ttu-id="45afe-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="45afe-113">The type of elements of the array.</span></span>