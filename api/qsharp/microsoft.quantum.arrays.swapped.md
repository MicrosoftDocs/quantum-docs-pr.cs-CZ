---
uid: Microsoft.Quantum.Arrays.Swapped
title: Swap – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850953"
---
# <a name="swapped-function"></a><span data-ttu-id="5cd83-102">Swap – funkce</span><span class="sxs-lookup"><span data-stu-id="5cd83-102">Swapped function</span></span>

<span data-ttu-id="5cd83-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5cd83-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5cd83-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5cd83-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5cd83-105">Použije záměnu dvou prvků v poli.</span><span class="sxs-lookup"><span data-stu-id="5cd83-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="5cd83-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5cd83-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="5cd83-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5cd83-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5cd83-108">Index prvního prvku, který má být prohozen.</span><span class="sxs-lookup"><span data-stu-id="5cd83-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="5cd83-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5cd83-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5cd83-110">Index druhého elementu, který se má zaměnit</span><span class="sxs-lookup"><span data-stu-id="5cd83-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="5cd83-111">Šipka: t []</span><span class="sxs-lookup"><span data-stu-id="5cd83-111">arr : 'T[]</span></span>

<span data-ttu-id="5cd83-112">Pole s prvky, které mají být prohozeny.</span><span class="sxs-lookup"><span data-stu-id="5cd83-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="5cd83-113">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="5cd83-113">Output : 'T[]</span></span>

<span data-ttu-id="5cd83-114">Pole s použitým přepnutím na místě</span><span class="sxs-lookup"><span data-stu-id="5cd83-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="5cd83-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="5cd83-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="5cd83-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5cd83-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5cd83-117">'S</span><span class="sxs-lookup"><span data-stu-id="5cd83-117">'T</span></span>

