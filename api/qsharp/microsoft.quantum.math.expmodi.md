---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857037"
---
# <a name="expmodi-function"></a><span data-ttu-id="ffb23-102">ExpModI – funkce</span><span class="sxs-lookup"><span data-stu-id="ffb23-102">ExpModI function</span></span>

<span data-ttu-id="ffb23-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ffb23-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ffb23-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ffb23-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ffb23-105">Vrátí celé číslo umocněné na daný příkon s ohledem na dané zbytky.</span><span class="sxs-lookup"><span data-stu-id="ffb23-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="ffb23-106">Popis</span><span class="sxs-lookup"><span data-stu-id="ffb23-106">Description</span></span>

<span data-ttu-id="ffb23-107">ExpBase $, Power by vám podíváme na to, co je to $x $, Power by $p $ a $N modulům.</span><span class="sxs-lookup"><span data-stu-id="ffb23-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="ffb23-108">Funkce vrátí $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="ffb23-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="ffb23-109">Předpokládáme, že $N $, $x $ jsou kladné a výkon je nezáporný.</span><span class="sxs-lookup"><span data-stu-id="ffb23-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="ffb23-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="ffb23-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="ffb23-111">expBase: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ffb23-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="ffb23-112">napájení: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ffb23-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="ffb23-113">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ffb23-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="ffb23-114">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ffb23-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="ffb23-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ffb23-115">Remarks</span></span>

<span data-ttu-id="ffb23-116">Doba trvá v poměru k počtu bitů v `power` , nikoli na `power` samotném.</span><span class="sxs-lookup"><span data-stu-id="ffb23-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>