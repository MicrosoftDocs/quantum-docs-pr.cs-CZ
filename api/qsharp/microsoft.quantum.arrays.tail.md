---
uid: Microsoft.Quantum.Arrays.Tail
title: Funkce tail
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 680562228a39263ef87ba053e6b7683412947e46
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845412"
---
# <a name="tail-function"></a><span data-ttu-id="5e04a-102">Funkce tail</span><span class="sxs-lookup"><span data-stu-id="5e04a-102">Tail function</span></span>

<span data-ttu-id="5e04a-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5e04a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5e04a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e04a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e04a-105">Vrátí poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="5e04a-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="5e04a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5e04a-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="5e04a-107">pole: ' A []</span><span class="sxs-lookup"><span data-stu-id="5e04a-107">array : 'A[]</span></span>

<span data-ttu-id="5e04a-108">Pole, jehož poslední prvek je pořízen.</span><span class="sxs-lookup"><span data-stu-id="5e04a-108">Array of which the last element is taken.</span></span> <span data-ttu-id="5e04a-109">Pole musí mít délku alespoň 1.</span><span class="sxs-lookup"><span data-stu-id="5e04a-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="5e04a-110">Výstup: ' A</span><span class="sxs-lookup"><span data-stu-id="5e04a-110">Output : 'A</span></span>

<span data-ttu-id="5e04a-111">Poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="5e04a-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5e04a-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5e04a-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="5e04a-113">A</span><span class="sxs-lookup"><span data-stu-id="5e04a-113">'A</span></span>

<span data-ttu-id="5e04a-114">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="5e04a-114">The type of the array elements.</span></span>