---
uid: Microsoft.Quantum.Logical.Xor
title: XOR – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: ae43545e19e81ed5da17c3d58c62ac0b7ee765f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708349"
---
# <a name="xor-function"></a><span data-ttu-id="64967-102">XOR – funkce</span><span class="sxs-lookup"><span data-stu-id="64967-102">Xor function</span></span>

<span data-ttu-id="64967-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="64967-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="64967-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64967-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="64967-105">Vrátí logickou nevýlučnou disjunkci dvou hodnot.</span><span class="sxs-lookup"><span data-stu-id="64967-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="64967-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="64967-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="64967-107">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="64967-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="64967-108">První hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="64967-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="64967-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="64967-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="64967-110">Druhá hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="64967-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="64967-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="64967-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="64967-112">`true` IF a je pouze v případě, že právě jedna z `a` a `b` je `true` .</span><span class="sxs-lookup"><span data-stu-id="64967-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>