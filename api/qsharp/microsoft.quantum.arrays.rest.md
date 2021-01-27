---
uid: Microsoft.Quantum.Arrays.Rest
title: REST – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: b6c579df354185a2defb08cd78bce816d8cc5959
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845478"
---
# <a name="rest-function"></a><span data-ttu-id="f186d-102">REST – funkce</span><span class="sxs-lookup"><span data-stu-id="f186d-102">Rest function</span></span>

<span data-ttu-id="f186d-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f186d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f186d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f186d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f186d-105">Vytvoří pole, které je rovno vstupnímu poli s výjimkou toho, že první prvek pole je vyřazen.</span><span class="sxs-lookup"><span data-stu-id="f186d-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="f186d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f186d-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="f186d-107">Array: t []</span><span class="sxs-lookup"><span data-stu-id="f186d-107">array : 'T[]</span></span>

<span data-ttu-id="f186d-108">Pole, jehož druhý k poslednímu prvku, je vytvoření výstupního pole.</span><span class="sxs-lookup"><span data-stu-id="f186d-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="f186d-109">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="f186d-109">Output : 'T[]</span></span>

<span data-ttu-id="f186d-110">Pole obsahující prvky `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="f186d-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f186d-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f186d-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f186d-112">'S</span><span class="sxs-lookup"><span data-stu-id="f186d-112">'T</span></span>

<span data-ttu-id="f186d-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="f186d-113">The type of the array elements.</span></span>