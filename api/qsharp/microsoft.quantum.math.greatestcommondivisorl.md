---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 77bdb040908e9a8af81dee09451a3582f7b7d159
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708499"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="7a8a9-102">GreatestCommonDivisorL – funkce</span><span class="sxs-lookup"><span data-stu-id="7a8a9-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="7a8a9-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7a8a9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7a8a9-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7a8a9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7a8a9-105">Vypočítá největšího společného dělitele $a $ a $b $.</span><span class="sxs-lookup"><span data-stu-id="7a8a9-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="7a8a9-106">GCD je vždy pozitivní.</span><span class="sxs-lookup"><span data-stu-id="7a8a9-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="7a8a9-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="7a8a9-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="7a8a9-108">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7a8a9-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7a8a9-109">první číslo, které je vypočítáno jako největšího nejdelšího společného dělitele</span><span class="sxs-lookup"><span data-stu-id="7a8a9-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="7a8a9-110">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7a8a9-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7a8a9-111">druhý počet, od kterého se počítá rozšířený největší dělitel</span><span class="sxs-lookup"><span data-stu-id="7a8a9-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="7a8a9-112">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7a8a9-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7a8a9-113">Největší společný dělitel $a $ a $b $</span><span class="sxs-lookup"><span data-stu-id="7a8a9-113">Greatest common divisor of $a$ and $b$</span></span>