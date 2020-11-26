---
uid: Microsoft.Quantum.Arrays.Flattened
title: Plochá funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 331b1714109259b21982e99d030aa0662e3aaadb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221211"
---
# <a name="flattened-function"></a><span data-ttu-id="f35f0-102">Plochá funkce</span><span class="sxs-lookup"><span data-stu-id="f35f0-102">Flattened function</span></span>

<span data-ttu-id="f35f0-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f35f0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f35f0-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f35f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f35f0-105">V případě pole polí vrací zřetězení všech polí.</span><span class="sxs-lookup"><span data-stu-id="f35f0-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="f35f0-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f35f0-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="f35f0-107">pole: t [] []</span><span class="sxs-lookup"><span data-stu-id="f35f0-107">arrays : 'T[][]</span></span>

<span data-ttu-id="f35f0-108">Pole polí.</span><span class="sxs-lookup"><span data-stu-id="f35f0-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="f35f0-109">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="f35f0-109">Output : 'T[]</span></span>

<span data-ttu-id="f35f0-110">Zřetězení všech polí</span><span class="sxs-lookup"><span data-stu-id="f35f0-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f35f0-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f35f0-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f35f0-112">'S</span><span class="sxs-lookup"><span data-stu-id="f35f0-112">'T</span></span>

<span data-ttu-id="f35f0-113">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="f35f0-113">The type of `array` elements.</span></span>