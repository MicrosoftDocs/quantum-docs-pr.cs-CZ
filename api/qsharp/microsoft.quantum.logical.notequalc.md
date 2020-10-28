---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: b26ad3515cb801b122858b9474aea76a0e5c498b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697252"
---
# <a name="notequalc-function"></a><span data-ttu-id="6e016-102">NotEqualC – funkce</span><span class="sxs-lookup"><span data-stu-id="6e016-102">NotEqualC function</span></span>

<span data-ttu-id="6e016-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6e016-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6e016-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6e016-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6e016-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="6e016-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="6e016-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6e016-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="6e016-107">a: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="6e016-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="6e016-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="6e016-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="6e016-109">b: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="6e016-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="6e016-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="6e016-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6e016-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6e016-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6e016-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="6e016-112">`true` if and only if `a` is not equal to `b`.</span></span>