---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 83bf5ba245038ad1c7c6ed4e8cdb493317276e6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817165"
---
# <a name="equalcp-function"></a><span data-ttu-id="65c9a-102">EqualCP – funkce</span><span class="sxs-lookup"><span data-stu-id="65c9a-102">EqualCP function</span></span>

<span data-ttu-id="65c9a-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="65c9a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="65c9a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65c9a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65c9a-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="65c9a-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="65c9a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="65c9a-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="65c9a-107">Odpověď: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="65c9a-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="65c9a-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="65c9a-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="65c9a-109">b: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="65c9a-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="65c9a-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="65c9a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="65c9a-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="65c9a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="65c9a-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="65c9a-112">`true` if and only if `a` is equal to `b`.</span></span>