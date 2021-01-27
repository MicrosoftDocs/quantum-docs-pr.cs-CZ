---
uid: Microsoft.Quantum.Arrays.Head
title: Head – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 6dd181914b5ed3ef16a02b31cb6131daf2a34e19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848575"
---
# <a name="head-function"></a><span data-ttu-id="db41a-102">Head – funkce</span><span class="sxs-lookup"><span data-stu-id="db41a-102">Head function</span></span>

<span data-ttu-id="db41a-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="db41a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="db41a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db41a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="db41a-105">Vrátí první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="db41a-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="db41a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="db41a-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="db41a-107">pole: ' A []</span><span class="sxs-lookup"><span data-stu-id="db41a-107">array : 'A[]</span></span>

<span data-ttu-id="db41a-108">Pole, jehož první prvek je pořízen.</span><span class="sxs-lookup"><span data-stu-id="db41a-108">Array of which the first element is taken.</span></span> <span data-ttu-id="db41a-109">Pole musí mít délku alespoň 1.</span><span class="sxs-lookup"><span data-stu-id="db41a-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="db41a-110">Výstup: ' A</span><span class="sxs-lookup"><span data-stu-id="db41a-110">Output : 'A</span></span>

<span data-ttu-id="db41a-111">První prvek pole.</span><span class="sxs-lookup"><span data-stu-id="db41a-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="db41a-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="db41a-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="db41a-113">A</span><span class="sxs-lookup"><span data-stu-id="db41a-113">'A</span></span>

<span data-ttu-id="db41a-114">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="db41a-114">The type of the array elements.</span></span>