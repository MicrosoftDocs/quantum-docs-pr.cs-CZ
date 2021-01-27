---
uid: Microsoft.Quantum.Logical.Xor
title: XOR – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: 4a4af7f628ca64170e046584d9caffe7ceee3d56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848453"
---
# <a name="xor-function"></a><span data-ttu-id="858f7-102">XOR – funkce</span><span class="sxs-lookup"><span data-stu-id="858f7-102">Xor function</span></span>

<span data-ttu-id="858f7-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="858f7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="858f7-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="858f7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="858f7-105">Vrátí logickou nevýlučnou disjunkci dvou hodnot.</span><span class="sxs-lookup"><span data-stu-id="858f7-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="858f7-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="858f7-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="858f7-107">Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="858f7-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="858f7-108">První hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="858f7-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="858f7-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="858f7-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="858f7-110">Druhá hodnota, která má být považována za.</span><span class="sxs-lookup"><span data-stu-id="858f7-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="858f7-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="858f7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="858f7-112">`true` IF a je pouze v případě, že právě jedna z `a` a `b` je `true` .</span><span class="sxs-lookup"><span data-stu-id="858f7-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>