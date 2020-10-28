---
uid: Microsoft.Quantum.Arrays.Flattened
title: Plochá funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 91a35f0ac2c2f8609bac07734265fcf4e88bf50b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706024"
---
# <a name="flattened-function"></a><span data-ttu-id="84560-102">Plochá funkce</span><span class="sxs-lookup"><span data-stu-id="84560-102">Flattened function</span></span>

<span data-ttu-id="84560-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="84560-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="84560-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="84560-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="84560-105">V případě pole polí vrací zřetězení všech polí.</span><span class="sxs-lookup"><span data-stu-id="84560-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="84560-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="84560-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="84560-107">pole: t [] []</span><span class="sxs-lookup"><span data-stu-id="84560-107">arrays : 'T[][]</span></span>

<span data-ttu-id="84560-108">Pole polí.</span><span class="sxs-lookup"><span data-stu-id="84560-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="84560-109">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="84560-109">Output : 'T[]</span></span>

<span data-ttu-id="84560-110">Zřetězení všech polí</span><span class="sxs-lookup"><span data-stu-id="84560-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="84560-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="84560-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="84560-112">'S</span><span class="sxs-lookup"><span data-stu-id="84560-112">'T</span></span>

<span data-ttu-id="84560-113">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="84560-113">The type of `array` elements.</span></span>