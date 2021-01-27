---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 0f545f7888f5a9a353cc6000a12988648ac82dd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856377"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="4c340-102">GreatestCommonDivisorL – funkce</span><span class="sxs-lookup"><span data-stu-id="4c340-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="4c340-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4c340-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4c340-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4c340-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4c340-105">Vypočítá největšího společného dělitele $a $ a $b $.</span><span class="sxs-lookup"><span data-stu-id="4c340-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="4c340-106">GCD je vždy pozitivní.</span><span class="sxs-lookup"><span data-stu-id="4c340-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="4c340-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="4c340-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4c340-108">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4c340-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4c340-109">první číslo, které je vypočítáno jako největšího nejdelšího společného dělitele</span><span class="sxs-lookup"><span data-stu-id="4c340-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="4c340-110">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4c340-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4c340-111">druhý počet, od kterého se počítá rozšířený největší dělitel</span><span class="sxs-lookup"><span data-stu-id="4c340-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="4c340-112">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4c340-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4c340-113">Největší společný dělitel $a $ a $b $</span><span class="sxs-lookup"><span data-stu-id="4c340-113">Greatest common divisor of $a$ and $b$</span></span>