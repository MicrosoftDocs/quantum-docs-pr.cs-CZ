---
uid: Microsoft.Quantum.Arrays.Padded
title: Čalouněná funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845569"
---
# <a name="padded-function"></a><span data-ttu-id="f6fd9-102">Čalouněná funkce</span><span class="sxs-lookup"><span data-stu-id="f6fd9-102">Padded function</span></span>

<span data-ttu-id="f6fd9-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f6fd9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f6fd9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f6fd9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f6fd9-105">Vrátí pole doplněné o zadané hodnoty až po zadanou délku.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="f6fd9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f6fd9-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="f6fd9-107">nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f6fd9-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f6fd9-108">Délka čalouněného pole.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-108">The length of the padded array.</span></span> <span data-ttu-id="f6fd9-109">Pokud je to pozitivní, `inputArray` je doplněna na hlavu.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="f6fd9-110">Pokud je tato hodnota záporná, `inputArray` je doplněna na konec.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="f6fd9-111">defaultElement: 'T</span><span class="sxs-lookup"><span data-stu-id="f6fd9-111">defaultElement : 'T</span></span>

<span data-ttu-id="f6fd9-112">Výchozí hodnota, která se má použít pro prvky odsazení</span><span class="sxs-lookup"><span data-stu-id="f6fd9-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="f6fd9-113">inputArray: t []</span><span class="sxs-lookup"><span data-stu-id="f6fd9-113">inputArray : 'T[]</span></span>

<span data-ttu-id="f6fd9-114">Pole, jehož hodnoty jsou na začátku výstupního pole.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="f6fd9-115">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="f6fd9-115">Output : 'T[]</span></span>

<span data-ttu-id="f6fd9-116">Pole `output` , které je `inputArray` doplněno na hlavu s s `defaultElement` až do `output` délky `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="f6fd9-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f6fd9-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f6fd9-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f6fd9-118">'S</span><span class="sxs-lookup"><span data-stu-id="f6fd9-118">'T</span></span>

<span data-ttu-id="f6fd9-119">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-119">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="f6fd9-120">Příklad</span><span class="sxs-lookup"><span data-stu-id="f6fd9-120">Example</span></span>

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```