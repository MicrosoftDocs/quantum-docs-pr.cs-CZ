---
uid: Microsoft.Quantum.Logical.Not
title: Nefunkční
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197445"
---
# <a name="not-function"></a><span data-ttu-id="ccde3-102">Nefunkční</span><span class="sxs-lookup"><span data-stu-id="ccde3-102">Not function</span></span>

<span data-ttu-id="ccde3-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ccde3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ccde3-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ccde3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ccde3-105">Vrátí logickou negaci hodnoty.</span><span class="sxs-lookup"><span data-stu-id="ccde3-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="ccde3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ccde3-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="ccde3-107">hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ccde3-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ccde3-108">Hodnota, která má být negace.</span><span class="sxs-lookup"><span data-stu-id="ccde3-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ccde3-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ccde3-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ccde3-110">`true` pouze v případě, že `value` je `false` .</span><span class="sxs-lookup"><span data-stu-id="ccde3-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ccde3-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ccde3-111">Remarks</span></span>

<span data-ttu-id="ccde3-112">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="ccde3-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```