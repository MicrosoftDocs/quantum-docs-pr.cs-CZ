---
uid: Microsoft.Quantum.Arrays.Swapped
title: Swap – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705745"
---
# <a name="swapped-function"></a><span data-ttu-id="cc926-102">Swap – funkce</span><span class="sxs-lookup"><span data-stu-id="cc926-102">Swapped function</span></span>

<span data-ttu-id="cc926-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cc926-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cc926-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cc926-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cc926-105">Použije záměnu dvou prvků v poli.</span><span class="sxs-lookup"><span data-stu-id="cc926-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="cc926-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cc926-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="cc926-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cc926-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cc926-108">Index prvního prvku, který má být prohozen.</span><span class="sxs-lookup"><span data-stu-id="cc926-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="cc926-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cc926-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cc926-110">Index druhého elementu, který se má zaměnit</span><span class="sxs-lookup"><span data-stu-id="cc926-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="cc926-111">Šipka: t []</span><span class="sxs-lookup"><span data-stu-id="cc926-111">arr : 'T[]</span></span>

<span data-ttu-id="cc926-112">Pole s prvky, které mají být prohozeny.</span><span class="sxs-lookup"><span data-stu-id="cc926-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="cc926-113">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="cc926-113">Output : 'T[]</span></span>

<span data-ttu-id="cc926-114">Pole s použitým přepnutím na místě</span><span class="sxs-lookup"><span data-stu-id="cc926-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="cc926-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="cc926-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="cc926-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="cc926-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cc926-117">'S</span><span class="sxs-lookup"><span data-stu-id="cc926-117">'T</span></span>

