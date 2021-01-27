---
uid: Microsoft.Quantum.Math.PowL
title: PowL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: f7282a3639ca87dae731e39594576aa73c4602ac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857469"
---
# <a name="powl-function"></a><span data-ttu-id="89951-102">PowL – funkce</span><span class="sxs-lookup"><span data-stu-id="89951-102">PowL function</span></span>

<span data-ttu-id="89951-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="89951-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="89951-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89951-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89951-105">Vrátí číslo umocněné na daný příkon.</span><span class="sxs-lookup"><span data-stu-id="89951-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="89951-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="89951-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="89951-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="89951-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="89951-108">Číslo $a $, které má být vyvoláno.</span><span class="sxs-lookup"><span data-stu-id="89951-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="89951-109">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89951-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="89951-110">$B pro napájení, na které $a $ má být vyvoláno.</span><span class="sxs-lookup"><span data-stu-id="89951-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="89951-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="89951-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="89951-112">$a napájení ^ b $</span><span class="sxs-lookup"><span data-stu-id="89951-112">The power $a^b$</span></span>