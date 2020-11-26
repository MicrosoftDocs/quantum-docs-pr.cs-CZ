---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210059"
---
# <a name="constantarray-function"></a><span data-ttu-id="2774f-102">ConstantArray – funkce</span><span class="sxs-lookup"><span data-stu-id="2774f-102">ConstantArray function</span></span>

<span data-ttu-id="2774f-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2774f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2774f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2774f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2774f-105">Vytvoří pole s danou délkou se všemi elementy, které se rovnají dané hodnotě.</span><span class="sxs-lookup"><span data-stu-id="2774f-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="2774f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2774f-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="2774f-107">Délka: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2774f-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2774f-108">Délka nového pole</span><span class="sxs-lookup"><span data-stu-id="2774f-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="2774f-109">hodnota: t</span><span class="sxs-lookup"><span data-stu-id="2774f-109">value : 'T</span></span>

<span data-ttu-id="2774f-110">Hodnota každého prvku nového pole.</span><span class="sxs-lookup"><span data-stu-id="2774f-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="2774f-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="2774f-111">Output : 'T[]</span></span>

<span data-ttu-id="2774f-112">Nové pole s délkou `length` , například každý prvek `value` .</span><span class="sxs-lookup"><span data-stu-id="2774f-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2774f-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2774f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2774f-114">'S</span><span class="sxs-lookup"><span data-stu-id="2774f-114">'T</span></span>

