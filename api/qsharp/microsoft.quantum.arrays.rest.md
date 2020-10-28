---
uid: Microsoft.Quantum.Arrays.Rest
title: REST – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705808"
---
# <a name="rest-function"></a><span data-ttu-id="a5446-102">REST – funkce</span><span class="sxs-lookup"><span data-stu-id="a5446-102">Rest function</span></span>

<span data-ttu-id="a5446-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a5446-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a5446-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5446-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5446-105">Vytvoří pole, které je rovno vstupnímu poli s výjimkou toho, že první prvek pole je vyřazen.</span><span class="sxs-lookup"><span data-stu-id="a5446-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="a5446-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a5446-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="a5446-107">Array: t []</span><span class="sxs-lookup"><span data-stu-id="a5446-107">array : 'T[]</span></span>

<span data-ttu-id="a5446-108">Pole, jehož druhý k poslednímu prvku, je vytvoření výstupního pole.</span><span class="sxs-lookup"><span data-stu-id="a5446-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="a5446-109">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="a5446-109">Output : 'T[]</span></span>

<span data-ttu-id="a5446-110">Pole obsahující prvky `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="a5446-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a5446-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a5446-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a5446-112">'S</span><span class="sxs-lookup"><span data-stu-id="a5446-112">'T</span></span>

<span data-ttu-id="a5446-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="a5446-113">The type of the array elements.</span></span>