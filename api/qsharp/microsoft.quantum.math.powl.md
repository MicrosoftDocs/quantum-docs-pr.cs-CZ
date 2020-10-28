---
uid: Microsoft.Quantum.Math.PowL
title: PowL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: 22c05cf85acf691490049ce9ac27a7c6b2a4899e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708973"
---
# <a name="powl-function"></a><span data-ttu-id="1152c-102">PowL – funkce</span><span class="sxs-lookup"><span data-stu-id="1152c-102">PowL function</span></span>

<span data-ttu-id="1152c-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1152c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1152c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1152c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1152c-105">Vrátí číslo umocněné na daný příkon.</span><span class="sxs-lookup"><span data-stu-id="1152c-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="1152c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="1152c-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="1152c-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1152c-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1152c-108">Číslo $a $, které má být vyvoláno.</span><span class="sxs-lookup"><span data-stu-id="1152c-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="1152c-109">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1152c-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1152c-110">$B pro napájení, na které $a $ má být vyvoláno.</span><span class="sxs-lookup"><span data-stu-id="1152c-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="1152c-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1152c-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1152c-112">$a napájení ^ b $</span><span class="sxs-lookup"><span data-stu-id="1152c-112">The power $a^b$</span></span>