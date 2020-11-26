---
uid: Microsoft.Quantum.Logical.Xor
title: XOR – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: afb94bd1fd0b791a9a7d84bc28b0cc2baf9a0938
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197088"
---
# <a name="xor-function"></a><span data-ttu-id="6aa3f-102">XOR – funkce</span><span class="sxs-lookup"><span data-stu-id="6aa3f-102">Xor function</span></span>

<span data-ttu-id="6aa3f-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6aa3f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6aa3f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6aa3f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6aa3f-105">Vrátí logickou nevýlučnou disjunkci dvou hodnot.</span><span class="sxs-lookup"><span data-stu-id="6aa3f-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="6aa3f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6aa3f-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="6aa3f-107">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6aa3f-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6aa3f-108">První hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="6aa3f-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="6aa3f-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6aa3f-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6aa3f-110">Druhá hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="6aa3f-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6aa3f-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6aa3f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6aa3f-112">`true` IF a je pouze v případě, že právě jedna z `a` a `b` je `true` .</span><span class="sxs-lookup"><span data-stu-id="6aa3f-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>