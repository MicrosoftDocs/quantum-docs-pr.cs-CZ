---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funkce výčtu
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221415"
---
# <a name="enumerated-function"></a><span data-ttu-id="ac044-102">Funkce výčtu</span><span class="sxs-lookup"><span data-stu-id="ac044-102">Enumerated function</span></span>

<span data-ttu-id="ac044-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ac044-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ac044-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac044-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac044-105">V případě pole, vrátí nové pole obsahující prvky původního pole spolu s indexy každého prvku.</span><span class="sxs-lookup"><span data-stu-id="ac044-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="ac044-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ac044-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="ac044-107">Array: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="ac044-107">array : 'TElement[]</span></span>

<span data-ttu-id="ac044-108">Pole, jehož prvky mají být vyčísleny.</span><span class="sxs-lookup"><span data-stu-id="ac044-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="ac044-109">Výstup: ([int](xref:microsoft.quantum.lang-ref.int), ' TElement) []</span><span class="sxs-lookup"><span data-stu-id="ac044-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="ac044-110">Nové pole obsahující prvky původního pole spolu s jejich indexy.</span><span class="sxs-lookup"><span data-stu-id="ac044-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ac044-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ac044-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="ac044-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="ac044-112">'TElement</span></span>

<span data-ttu-id="ac044-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="ac044-113">The type of elements of the array.</span></span>