---
uid: Microsoft.Quantum.Math.PowI
title: PowI – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowI
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: c4e59f7c398a88485ada9d2b313b93aac530ce02
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857483"
---
# <a name="powi-function"></a><span data-ttu-id="5e23a-102">PowI – funkce</span><span class="sxs-lookup"><span data-stu-id="5e23a-102">PowI function</span></span>

<span data-ttu-id="5e23a-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5e23a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5e23a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e23a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e23a-105">Vrátí číslo umocněné na daný příkon.</span><span class="sxs-lookup"><span data-stu-id="5e23a-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowI (a : Int, power : Int) : Int
```


## <a name="input"></a><span data-ttu-id="5e23a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5e23a-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="5e23a-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5e23a-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5e23a-108">Číslo $a $, které má být vyvoláno.</span><span class="sxs-lookup"><span data-stu-id="5e23a-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="5e23a-109">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5e23a-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5e23a-110">$B pro napájení, na které $a $ má být vyvoláno.</span><span class="sxs-lookup"><span data-stu-id="5e23a-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--int"></a><span data-ttu-id="5e23a-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5e23a-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5e23a-112">$a napájení ^ b $</span><span class="sxs-lookup"><span data-stu-id="5e23a-112">The power $a^b$</span></span>