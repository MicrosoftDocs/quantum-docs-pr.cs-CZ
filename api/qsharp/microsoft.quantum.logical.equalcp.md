---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: c8ee7e6a04cc2478f1c97fcc1d964a1574f7b1fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707033"
---
# <a name="equalcp-function"></a><span data-ttu-id="52ae7-102">EqualCP – funkce</span><span class="sxs-lookup"><span data-stu-id="52ae7-102">EqualCP function</span></span>

<span data-ttu-id="52ae7-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="52ae7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="52ae7-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="52ae7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="52ae7-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="52ae7-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="52ae7-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="52ae7-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="52ae7-107">Odpověď: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="52ae7-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="52ae7-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="52ae7-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="52ae7-109">b: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="52ae7-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="52ae7-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="52ae7-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="52ae7-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="52ae7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="52ae7-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="52ae7-112">`true` if and only if `a` is equal to `b`.</span></span>