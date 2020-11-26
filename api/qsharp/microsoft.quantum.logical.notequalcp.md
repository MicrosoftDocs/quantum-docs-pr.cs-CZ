---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: df735408f76eb6b88f0d867021d69b83edd69b7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197292"
---
# <a name="notequalcp-function"></a><span data-ttu-id="82c6a-102">NotEqualCP – funkce</span><span class="sxs-lookup"><span data-stu-id="82c6a-102">NotEqualCP function</span></span>

<span data-ttu-id="82c6a-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="82c6a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="82c6a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="82c6a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="82c6a-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="82c6a-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="82c6a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="82c6a-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="82c6a-107">Odpověď: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="82c6a-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="82c6a-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="82c6a-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="82c6a-109">b: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="82c6a-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="82c6a-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="82c6a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="82c6a-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="82c6a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="82c6a-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="82c6a-112">`true` if and only if `a` is not equal to `b`.</span></span>