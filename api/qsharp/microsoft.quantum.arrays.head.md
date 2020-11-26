---
uid: Microsoft.Quantum.Arrays.Head
title: Head – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 834cbe2384122463be6a0efcb6e09785aae9c092
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221109"
---
# <a name="head-function"></a><span data-ttu-id="f6a44-102">Head – funkce</span><span class="sxs-lookup"><span data-stu-id="f6a44-102">Head function</span></span>

<span data-ttu-id="f6a44-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f6a44-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f6a44-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f6a44-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f6a44-105">Vrátí první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="f6a44-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="f6a44-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f6a44-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="f6a44-107">pole: ' A []</span><span class="sxs-lookup"><span data-stu-id="f6a44-107">array : 'A[]</span></span>

<span data-ttu-id="f6a44-108">Pole, jehož první prvek je pořízen.</span><span class="sxs-lookup"><span data-stu-id="f6a44-108">Array of which the first element is taken.</span></span> <span data-ttu-id="f6a44-109">Pole musí mít délku alespoň 1.</span><span class="sxs-lookup"><span data-stu-id="f6a44-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="f6a44-110">Výstup: ' A</span><span class="sxs-lookup"><span data-stu-id="f6a44-110">Output : 'A</span></span>

<span data-ttu-id="f6a44-111">První prvek pole.</span><span class="sxs-lookup"><span data-stu-id="f6a44-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f6a44-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f6a44-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="f6a44-113">A</span><span class="sxs-lookup"><span data-stu-id="f6a44-113">'A</span></span>

<span data-ttu-id="f6a44-114">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="f6a44-114">The type of the array elements.</span></span>