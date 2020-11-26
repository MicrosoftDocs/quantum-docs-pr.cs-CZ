---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: e3175b9b6fd2890963de0452102e2f0de1026b91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198227"
---
# <a name="equalcp-function"></a><span data-ttu-id="c6861-102">EqualCP – funkce</span><span class="sxs-lookup"><span data-stu-id="c6861-102">EqualCP function</span></span>

<span data-ttu-id="c6861-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c6861-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c6861-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c6861-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c6861-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="c6861-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="c6861-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c6861-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="c6861-107">Odpověď: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="c6861-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="c6861-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="c6861-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="c6861-109">b: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="c6861-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="c6861-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="c6861-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c6861-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c6861-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c6861-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="c6861-112">`true` if and only if `a` is equal to `b`.</span></span>