---
uid: Microsoft.Quantum.Logical.EqualC
title: EqualC – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualC
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 4c511489888613d95adaf154c005b3211af75446
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198380"
---
# <a name="equalc-function"></a><span data-ttu-id="c0658-102">EqualC – funkce</span><span class="sxs-lookup"><span data-stu-id="c0658-102">EqualC function</span></span>

<span data-ttu-id="c0658-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c0658-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c0658-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0658-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0658-105">Vrátí hodnotu true pouze v případě, že jsou dva vstupy stejné.</span><span class="sxs-lookup"><span data-stu-id="c0658-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="c0658-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c0658-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="c0658-107">a: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="c0658-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="c0658-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="c0658-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="c0658-109">b: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="c0658-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="c0658-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="c0658-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c0658-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c0658-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c0658-112">`true` pouze v případě, že `a` je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="c0658-112">`true` if and only if `a` is equal to `b`.</span></span>