---
uid: Microsoft.Quantum.Logical.Not
title: Nefunkční
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849077"
---
# <a name="not-function"></a><span data-ttu-id="c2163-102">Nefunkční</span><span class="sxs-lookup"><span data-stu-id="c2163-102">Not function</span></span>

<span data-ttu-id="c2163-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c2163-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c2163-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c2163-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c2163-105">Vrátí logickou negaci hodnoty.</span><span class="sxs-lookup"><span data-stu-id="c2163-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="c2163-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c2163-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="c2163-107">hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c2163-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c2163-108">Hodnota, která má být negace.</span><span class="sxs-lookup"><span data-stu-id="c2163-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c2163-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c2163-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c2163-110">`true` pouze v případě, že `value` je `false` .</span><span class="sxs-lookup"><span data-stu-id="c2163-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c2163-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c2163-111">Remarks</span></span>

<span data-ttu-id="c2163-112">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="c2163-112">The following are equivalent:</span></span>

```qsharp
let x = not value;
let x = Not(value);
```