---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Funkce prefixs
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845509"
---
# <a name="prefixes-function"></a><span data-ttu-id="828e8-102">Funkce prefixs</span><span class="sxs-lookup"><span data-stu-id="828e8-102">Prefixes function</span></span>

<span data-ttu-id="828e8-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="828e8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="828e8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="828e8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="828e8-105">Předanému poli vrátí všechny jeho předpony.</span><span class="sxs-lookup"><span data-stu-id="828e8-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="828e8-106">Popis</span><span class="sxs-lookup"><span data-stu-id="828e8-106">Description</span></span>

<span data-ttu-id="828e8-107">Vrátí pole všech předpon počínaje polem, které má pouze první prvek do kompletního pole.</span><span class="sxs-lookup"><span data-stu-id="828e8-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="828e8-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="828e8-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="828e8-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="828e8-109">array : 'T[]</span></span>

<span data-ttu-id="828e8-110">Pole prvků.</span><span class="sxs-lookup"><span data-stu-id="828e8-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="828e8-111">Výstup: t [] []</span><span class="sxs-lookup"><span data-stu-id="828e8-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="828e8-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="828e8-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="828e8-113">'S</span><span class="sxs-lookup"><span data-stu-id="828e8-113">'T</span></span>

<span data-ttu-id="828e8-114">Typ `array` prvků.</span><span class="sxs-lookup"><span data-stu-id="828e8-114">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="828e8-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="828e8-115">Example</span></span>

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```