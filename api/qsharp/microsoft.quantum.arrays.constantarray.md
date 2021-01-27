---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846228"
---
# <a name="constantarray-function"></a><span data-ttu-id="2e07d-102">ConstantArray – funkce</span><span class="sxs-lookup"><span data-stu-id="2e07d-102">ConstantArray function</span></span>

<span data-ttu-id="2e07d-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2e07d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2e07d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e07d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e07d-105">Vytvoří pole s danou délkou se všemi elementy, které se rovnají dané hodnotě.</span><span class="sxs-lookup"><span data-stu-id="2e07d-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="2e07d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2e07d-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="2e07d-107">Délka: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2e07d-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2e07d-108">Délka nového pole</span><span class="sxs-lookup"><span data-stu-id="2e07d-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="2e07d-109">hodnota: t</span><span class="sxs-lookup"><span data-stu-id="2e07d-109">value : 'T</span></span>

<span data-ttu-id="2e07d-110">Hodnota každého prvku nového pole.</span><span class="sxs-lookup"><span data-stu-id="2e07d-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="2e07d-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="2e07d-111">Output : 'T[]</span></span>

<span data-ttu-id="2e07d-112">Nové pole s délkou `length` , například každý prvek `value` .</span><span class="sxs-lookup"><span data-stu-id="2e07d-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2e07d-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2e07d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2e07d-114">'S</span><span class="sxs-lookup"><span data-stu-id="2e07d-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="2e07d-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="2e07d-115">Example</span></span>

<span data-ttu-id="2e07d-116">Následující kód vytvoří pole 3 logických hodnot, každé se rovná `true` :</span><span class="sxs-lookup"><span data-stu-id="2e07d-116">The following code creates an array of 3 Boolean values, each equal to `true`:</span></span>

```qsharp
let array = ConstantArray(3, true);
```