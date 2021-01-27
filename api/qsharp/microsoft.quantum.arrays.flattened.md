---
uid: Microsoft.Quantum.Arrays.Flattened
title: Plochá funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 272533d4efd8598b21daa341c867c070a2083ce0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848615"
---
# <a name="flattened-function"></a><span data-ttu-id="f5a24-102">Plochá funkce</span><span class="sxs-lookup"><span data-stu-id="f5a24-102">Flattened function</span></span>

<span data-ttu-id="f5a24-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f5a24-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f5a24-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5a24-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5a24-105">V případě pole polí vrací zřetězení všech polí.</span><span class="sxs-lookup"><span data-stu-id="f5a24-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="f5a24-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f5a24-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="f5a24-107">pole: t [] []</span><span class="sxs-lookup"><span data-stu-id="f5a24-107">arrays : 'T[][]</span></span>

<span data-ttu-id="f5a24-108">Pole polí.</span><span class="sxs-lookup"><span data-stu-id="f5a24-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="f5a24-109">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="f5a24-109">Output : 'T[]</span></span>

<span data-ttu-id="f5a24-110">Zřetězení všech polí</span><span class="sxs-lookup"><span data-stu-id="f5a24-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f5a24-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f5a24-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f5a24-112">'S</span><span class="sxs-lookup"><span data-stu-id="f5a24-112">'T</span></span>

<span data-ttu-id="f5a24-113">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="f5a24-113">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="f5a24-114">Příklad</span><span class="sxs-lookup"><span data-stu-id="f5a24-114">Example</span></span>

```qsharp
let flattened = Flattened([[1, 2], [3], [4, 5, 6]]);
// flattened = [1, 2, 3, 4, 5, 6]
```