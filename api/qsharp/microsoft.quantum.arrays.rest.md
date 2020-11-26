---
uid: Microsoft.Quantum.Arrays.Rest
title: REST – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: 4dd10b6e8839fd906ca9c2e36c89c626d5772149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220383"
---
# <a name="rest-function"></a><span data-ttu-id="b77fa-102">REST – funkce</span><span class="sxs-lookup"><span data-stu-id="b77fa-102">Rest function</span></span>

<span data-ttu-id="b77fa-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b77fa-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b77fa-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b77fa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b77fa-105">Vytvoří pole, které je rovno vstupnímu poli s výjimkou toho, že první prvek pole je vyřazen.</span><span class="sxs-lookup"><span data-stu-id="b77fa-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b77fa-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b77fa-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="b77fa-107">Array: t []</span><span class="sxs-lookup"><span data-stu-id="b77fa-107">array : 'T[]</span></span>

<span data-ttu-id="b77fa-108">Pole, jehož druhý k poslednímu prvku, je vytvoření výstupního pole.</span><span class="sxs-lookup"><span data-stu-id="b77fa-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="b77fa-109">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="b77fa-109">Output : 'T[]</span></span>

<span data-ttu-id="b77fa-110">Pole obsahující prvky `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="b77fa-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b77fa-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b77fa-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b77fa-112">'S</span><span class="sxs-lookup"><span data-stu-id="b77fa-112">'T</span></span>

<span data-ttu-id="b77fa-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="b77fa-113">The type of the array elements.</span></span>