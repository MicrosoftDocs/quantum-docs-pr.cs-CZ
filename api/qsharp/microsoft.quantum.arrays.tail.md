---
uid: Microsoft.Quantum.Arrays.Tail
title: Funkce tail
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7a1eb2afefd662f90e58798b56bc83b34ac2abfd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705744"
---
# <a name="tail-function"></a><span data-ttu-id="2c7fd-102">Funkce tail</span><span class="sxs-lookup"><span data-stu-id="2c7fd-102">Tail function</span></span>

<span data-ttu-id="2c7fd-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2c7fd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2c7fd-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c7fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c7fd-105">Vrátí poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="2c7fd-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="2c7fd-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2c7fd-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="2c7fd-107">pole: ' A []</span><span class="sxs-lookup"><span data-stu-id="2c7fd-107">array : 'A[]</span></span>

<span data-ttu-id="2c7fd-108">Pole, jehož poslední prvek je pořízen.</span><span class="sxs-lookup"><span data-stu-id="2c7fd-108">Array of which the last element is taken.</span></span> <span data-ttu-id="2c7fd-109">Pole musí mít délku alespoň 1.</span><span class="sxs-lookup"><span data-stu-id="2c7fd-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="2c7fd-110">Výstup: ' A</span><span class="sxs-lookup"><span data-stu-id="2c7fd-110">Output : 'A</span></span>

<span data-ttu-id="2c7fd-111">Poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="2c7fd-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2c7fd-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2c7fd-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="2c7fd-113">A</span><span class="sxs-lookup"><span data-stu-id="2c7fd-113">'A</span></span>

<span data-ttu-id="2c7fd-114">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="2c7fd-114">The type of the array elements.</span></span>