---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorI
title: GreatestCommonDivisorI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorI
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 7fd891aa2e4753020ec9ac4e702f8af9edc9df0a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708500"
---
# <a name="greatestcommondivisori-function"></a><span data-ttu-id="e4615-102">GreatestCommonDivisorI – funkce</span><span class="sxs-lookup"><span data-stu-id="e4615-102">GreatestCommonDivisorI function</span></span>

<span data-ttu-id="e4615-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e4615-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e4615-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4615-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4615-105">Vypočítá největšího společného dělitele $a $ a $b $.</span><span class="sxs-lookup"><span data-stu-id="e4615-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="e4615-106">GCD je vždy pozitivní.</span><span class="sxs-lookup"><span data-stu-id="e4615-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="e4615-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="e4615-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="e4615-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4615-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4615-109">první číslo, které je vypočítáno jako největšího nejdelšího společného dělitele</span><span class="sxs-lookup"><span data-stu-id="e4615-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="e4615-110">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4615-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4615-111">druhý počet, od kterého se počítá rozšířený největší dělitel</span><span class="sxs-lookup"><span data-stu-id="e4615-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--int"></a><span data-ttu-id="e4615-112">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4615-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4615-113">Největší společný dělitel $a $ a $b $</span><span class="sxs-lookup"><span data-stu-id="e4615-113">Greatest common divisor of $a$ and $b$</span></span>