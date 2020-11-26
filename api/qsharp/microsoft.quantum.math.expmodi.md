---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 197f7351ce76ebb7684ca8014cab9ab65d9c784c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228486"
---
# <a name="expmodi-function"></a><span data-ttu-id="b2072-102">ExpModI – funkce</span><span class="sxs-lookup"><span data-stu-id="b2072-102">ExpModI function</span></span>

<span data-ttu-id="b2072-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b2072-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b2072-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2072-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2072-105">Vrátí celé číslo umocněné na daný příkon s ohledem na dané zbytky.</span><span class="sxs-lookup"><span data-stu-id="b2072-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="b2072-106">Popis</span><span class="sxs-lookup"><span data-stu-id="b2072-106">Description</span></span>

<span data-ttu-id="b2072-107">ExpBase $, Power by vám podíváme na to, co je to $x $, Power by $p $ a $N modulům.</span><span class="sxs-lookup"><span data-stu-id="b2072-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="b2072-108">Funkce vrátí $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="b2072-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="b2072-109">Předpokládáme, že $N $, $x $ jsou kladné a výkon je nezáporný.</span><span class="sxs-lookup"><span data-stu-id="b2072-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="b2072-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="b2072-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="b2072-111">expBase: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b2072-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="b2072-112">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b2072-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="b2072-113">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b2072-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="b2072-114">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b2072-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="b2072-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b2072-115">Remarks</span></span>

<span data-ttu-id="b2072-116">Doba trvá v poměru k počtu bitů v `power` , nikoli na `power` samotném.</span><span class="sxs-lookup"><span data-stu-id="b2072-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>