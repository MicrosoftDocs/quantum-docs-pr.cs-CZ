---
uid: Microsoft.Quantum.Logical.EqualC
title: EqualC – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualC
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 8b0c34915ef392e8a84706f601da71f3848a3134
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707041"
---
# <a name="equalc-function"></a><span data-ttu-id="f1d0a-102">EqualC – funkce</span><span class="sxs-lookup"><span data-stu-id="f1d0a-102">EqualC function</span></span>

<span data-ttu-id="f1d0a-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f1d0a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f1d0a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f1d0a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f1d0a-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="f1d0a-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="f1d0a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f1d0a-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="f1d0a-107">a: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="f1d0a-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="f1d0a-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="f1d0a-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="f1d0a-109">b: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="f1d0a-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="f1d0a-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="f1d0a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f1d0a-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f1d0a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f1d0a-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="f1d0a-112">`true` if and only if `a` is equal to `b`.</span></span>