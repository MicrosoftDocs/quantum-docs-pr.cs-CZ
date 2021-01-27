---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: b19de2e4e8052c77118f341700357b212e20af53
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849030"
---
# <a name="notequall-function"></a><span data-ttu-id="31cd2-102">NotEqualL – funkce</span><span class="sxs-lookup"><span data-stu-id="31cd2-102">NotEqualL function</span></span>

<span data-ttu-id="31cd2-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="31cd2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="31cd2-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="31cd2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="31cd2-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="31cd2-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="31cd2-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="31cd2-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="31cd2-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="31cd2-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="31cd2-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="31cd2-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="31cd2-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="31cd2-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="31cd2-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="31cd2-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="31cd2-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="31cd2-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="31cd2-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="31cd2-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="31cd2-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="31cd2-113">Remarks</span></span>

<span data-ttu-id="31cd2-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="31cd2-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualL(a, b);
```