---
uid: Microsoft.Quantum.Arrays.Tail
title: Funkce tail
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7084cd8bc75f295024dce361153b58490074cdc5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220089"
---
# <a name="tail-function"></a><span data-ttu-id="4cff3-102">Funkce tail</span><span class="sxs-lookup"><span data-stu-id="4cff3-102">Tail function</span></span>

<span data-ttu-id="4cff3-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4cff3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4cff3-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4cff3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4cff3-105">Vrátí poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="4cff3-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="4cff3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4cff3-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="4cff3-107">pole: ' A []</span><span class="sxs-lookup"><span data-stu-id="4cff3-107">array : 'A[]</span></span>

<span data-ttu-id="4cff3-108">Pole, jehož poslední prvek je pořízen.</span><span class="sxs-lookup"><span data-stu-id="4cff3-108">Array of which the last element is taken.</span></span> <span data-ttu-id="4cff3-109">Pole musí mít délku alespoň 1.</span><span class="sxs-lookup"><span data-stu-id="4cff3-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="4cff3-110">Výstup: ' A</span><span class="sxs-lookup"><span data-stu-id="4cff3-110">Output : 'A</span></span>

<span data-ttu-id="4cff3-111">Poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="4cff3-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4cff3-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4cff3-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="4cff3-113">A</span><span class="sxs-lookup"><span data-stu-id="4cff3-113">'A</span></span>

<span data-ttu-id="4cff3-114">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="4cff3-114">The type of the array elements.</span></span>