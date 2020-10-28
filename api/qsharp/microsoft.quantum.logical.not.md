---
uid: Microsoft.Quantum.Logical.Not
title: Nefunkční
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697264"
---
# <a name="not-function"></a><span data-ttu-id="cc69e-102">Nefunkční</span><span class="sxs-lookup"><span data-stu-id="cc69e-102">Not function</span></span>

<span data-ttu-id="cc69e-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cc69e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cc69e-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cc69e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cc69e-105">Vrátí logickou negaci hodnoty.</span><span class="sxs-lookup"><span data-stu-id="cc69e-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="cc69e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cc69e-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="cc69e-107">hodnota: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cc69e-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cc69e-108">Hodnota, která má být negace.</span><span class="sxs-lookup"><span data-stu-id="cc69e-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cc69e-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cc69e-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cc69e-110">`true` pouze v případě, že `value` je `false` .</span><span class="sxs-lookup"><span data-stu-id="cc69e-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc69e-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="cc69e-111">Remarks</span></span>

<span data-ttu-id="cc69e-112">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="cc69e-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```