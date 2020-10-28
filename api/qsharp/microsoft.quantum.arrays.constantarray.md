---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706137"
---
# <a name="constantarray-function"></a><span data-ttu-id="5c86a-102">ConstantArray – funkce</span><span class="sxs-lookup"><span data-stu-id="5c86a-102">ConstantArray function</span></span>

<span data-ttu-id="5c86a-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5c86a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5c86a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c86a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c86a-105">Vytvoří pole s danou délkou se všemi elementy, které se rovnají dané hodnotě.</span><span class="sxs-lookup"><span data-stu-id="5c86a-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="5c86a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5c86a-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="5c86a-107">Délka: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5c86a-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5c86a-108">Délka nového pole</span><span class="sxs-lookup"><span data-stu-id="5c86a-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="5c86a-109">hodnota: t</span><span class="sxs-lookup"><span data-stu-id="5c86a-109">value : 'T</span></span>

<span data-ttu-id="5c86a-110">Hodnota každého prvku nového pole.</span><span class="sxs-lookup"><span data-stu-id="5c86a-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="5c86a-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="5c86a-111">Output : 'T[]</span></span>

<span data-ttu-id="5c86a-112">Nové pole s délkou `length` , například každý prvek `value` .</span><span class="sxs-lookup"><span data-stu-id="5c86a-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5c86a-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5c86a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5c86a-114">'S</span><span class="sxs-lookup"><span data-stu-id="5c86a-114">'T</span></span>

