---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 81dd998353f674d55afe85dd20904047391bdb40
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707024"
---
# <a name="notequalcp-function"></a><span data-ttu-id="754d8-102">NotEqualCP – funkce</span><span class="sxs-lookup"><span data-stu-id="754d8-102">NotEqualCP function</span></span>

<span data-ttu-id="754d8-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="754d8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="754d8-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="754d8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="754d8-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="754d8-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="754d8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="754d8-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="754d8-107">Odpověď: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="754d8-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="754d8-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="754d8-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="754d8-109">b: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="754d8-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="754d8-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="754d8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="754d8-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="754d8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="754d8-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="754d8-112">`true` if and only if `a` is not equal to `b`.</span></span>