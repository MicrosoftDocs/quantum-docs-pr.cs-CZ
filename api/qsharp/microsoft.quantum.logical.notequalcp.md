---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 85225109a3822a9b63a231631f3d7265143418b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814401"
---
# <a name="notequalcp-function"></a><span data-ttu-id="de3ec-102">NotEqualCP – funkce</span><span class="sxs-lookup"><span data-stu-id="de3ec-102">NotEqualCP function</span></span>

<span data-ttu-id="de3ec-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="de3ec-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="de3ec-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="de3ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="de3ec-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="de3ec-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="de3ec-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="de3ec-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="de3ec-107">Odpověď: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="de3ec-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="de3ec-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="de3ec-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="de3ec-109">b: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="de3ec-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="de3ec-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="de3ec-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="de3ec-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="de3ec-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="de3ec-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="de3ec-112">`true` if and only if `a` is not equal to `b`.</span></span>