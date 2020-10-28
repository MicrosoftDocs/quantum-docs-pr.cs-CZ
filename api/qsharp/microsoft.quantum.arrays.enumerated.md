---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funkce výčtu
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706065"
---
# <a name="enumerated-function"></a><span data-ttu-id="3c0f5-102">Funkce výčtu</span><span class="sxs-lookup"><span data-stu-id="3c0f5-102">Enumerated function</span></span>

<span data-ttu-id="3c0f5-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3c0f5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3c0f5-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c0f5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c0f5-105">V případě pole, vrátí nové pole obsahující prvky původního pole spolu s indexy každého prvku.</span><span class="sxs-lookup"><span data-stu-id="3c0f5-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="3c0f5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3c0f5-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="3c0f5-107">Array: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="3c0f5-107">array : 'TElement[]</span></span>

<span data-ttu-id="3c0f5-108">Pole, jehož prvky mají být vyčísleny.</span><span class="sxs-lookup"><span data-stu-id="3c0f5-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="3c0f5-109">Výstup: ([int](xref:microsoft.quantum.lang-ref.int), ' TElement) []</span><span class="sxs-lookup"><span data-stu-id="3c0f5-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="3c0f5-110">Nové pole obsahující prvky původního pole spolu s jejich indexy.</span><span class="sxs-lookup"><span data-stu-id="3c0f5-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3c0f5-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="3c0f5-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="3c0f5-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="3c0f5-112">'TElement</span></span>

<span data-ttu-id="3c0f5-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="3c0f5-113">The type of elements of the array.</span></span>