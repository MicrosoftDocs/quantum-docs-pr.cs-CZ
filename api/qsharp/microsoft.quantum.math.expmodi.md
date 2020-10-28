---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708379"
---
# <a name="expmodi-function"></a><span data-ttu-id="f4964-102">ExpModI – funkce</span><span class="sxs-lookup"><span data-stu-id="f4964-102">ExpModI function</span></span>

<span data-ttu-id="f4964-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f4964-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f4964-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4964-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4964-105">Vrátí celé číslo umocněné na daný příkon s ohledem na dané zbytky.</span><span class="sxs-lookup"><span data-stu-id="f4964-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="f4964-106">Popis</span><span class="sxs-lookup"><span data-stu-id="f4964-106">Description</span></span>

<span data-ttu-id="f4964-107">ExpBase $, Power by vám podíváme na to, co je to $x $, Power by $p $ a $N modulům.</span><span class="sxs-lookup"><span data-stu-id="f4964-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="f4964-108">Funkce vrátí $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="f4964-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="f4964-109">Předpokládáme, že $N $, $x $ jsou kladné a výkon je nezáporný.</span><span class="sxs-lookup"><span data-stu-id="f4964-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="f4964-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="f4964-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="f4964-111">expBase: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4964-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="f4964-112">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4964-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="f4964-113">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4964-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="f4964-114">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4964-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="f4964-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f4964-115">Remarks</span></span>

<span data-ttu-id="f4964-116">Doba trvá v poměru k počtu bitů v `power` , nikoli na `power` samotném.</span><span class="sxs-lookup"><span data-stu-id="f4964-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>