---
uid: Microsoft.Quantum.Arrays.Padded
title: Čalouněná funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705849"
---
# <a name="padded-function"></a><span data-ttu-id="1ba29-102">Čalouněná funkce</span><span class="sxs-lookup"><span data-stu-id="1ba29-102">Padded function</span></span>

<span data-ttu-id="1ba29-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1ba29-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1ba29-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1ba29-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1ba29-105">Vrátí pole doplněné o zadané hodnoty až po zadanou délku.</span><span class="sxs-lookup"><span data-stu-id="1ba29-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="1ba29-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="1ba29-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="1ba29-107">nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1ba29-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1ba29-108">Délka čalouněného pole.</span><span class="sxs-lookup"><span data-stu-id="1ba29-108">The length of the padded array.</span></span> <span data-ttu-id="1ba29-109">Pokud je to pozitivní, `inputArray` je doplněna na hlavu.</span><span class="sxs-lookup"><span data-stu-id="1ba29-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="1ba29-110">Pokud je tato hodnota záporná, `inputArray` je doplněna na konec.</span><span class="sxs-lookup"><span data-stu-id="1ba29-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="1ba29-111">defaultElement: 'T</span><span class="sxs-lookup"><span data-stu-id="1ba29-111">defaultElement : 'T</span></span>

<span data-ttu-id="1ba29-112">Výchozí hodnota, která se má použít pro prvky odsazení</span><span class="sxs-lookup"><span data-stu-id="1ba29-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="1ba29-113">inputArray: t []</span><span class="sxs-lookup"><span data-stu-id="1ba29-113">inputArray : 'T[]</span></span>

<span data-ttu-id="1ba29-114">Pole, jehož hodnoty jsou na začátku výstupního pole.</span><span class="sxs-lookup"><span data-stu-id="1ba29-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="1ba29-115">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="1ba29-115">Output : 'T[]</span></span>

<span data-ttu-id="1ba29-116">Pole `output` , které je `inputArray` doplněno na hlavu s s `defaultElement` až do `output` délky `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="1ba29-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1ba29-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="1ba29-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1ba29-118">'S</span><span class="sxs-lookup"><span data-stu-id="1ba29-118">'T</span></span>

<span data-ttu-id="1ba29-119">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="1ba29-119">The type of the array elements.</span></span>