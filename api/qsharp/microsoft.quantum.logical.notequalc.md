---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 33049b09405529bd418ff8652b6cb0f11bf734f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849057"
---
# <a name="notequalc-function"></a><span data-ttu-id="543da-102">NotEqualC – funkce</span><span class="sxs-lookup"><span data-stu-id="543da-102">NotEqualC function</span></span>

<span data-ttu-id="543da-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="543da-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="543da-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="543da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="543da-105">Vrátí hodnotu true pouze v případě, že se neshodují dva vstupy.</span><span class="sxs-lookup"><span data-stu-id="543da-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="543da-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="543da-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="543da-107">a: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="543da-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="543da-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="543da-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="543da-109">b: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="543da-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="543da-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="543da-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="543da-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="543da-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="543da-112">`true` pouze pokud `a` se nerovná `b` .</span><span class="sxs-lookup"><span data-stu-id="543da-112">`true` if and only if `a` is not equal to `b`.</span></span>