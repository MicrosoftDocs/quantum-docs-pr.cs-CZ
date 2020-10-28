---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708535"
---
# <a name="expmodl-function"></a><span data-ttu-id="da59b-102">ExpModL – funkce</span><span class="sxs-lookup"><span data-stu-id="da59b-102">ExpModL function</span></span>

<span data-ttu-id="da59b-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="da59b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="da59b-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="da59b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="da59b-105">Vrátí celé číslo umocněné na daný příkon s ohledem na dané zbytky.</span><span class="sxs-lookup"><span data-stu-id="da59b-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="da59b-106">Popis</span><span class="sxs-lookup"><span data-stu-id="da59b-106">Description</span></span>

<span data-ttu-id="da59b-107">ExpBase $, Power by vám podíváme na to, co je to $x $, Power by $p $ a $N modulům.</span><span class="sxs-lookup"><span data-stu-id="da59b-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="da59b-108">Funkce vrátí $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="da59b-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="da59b-109">Předpokládáme, že $N $, $x $ jsou kladné a výkon je nezáporný.</span><span class="sxs-lookup"><span data-stu-id="da59b-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="da59b-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="da59b-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="da59b-111">expBase: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="da59b-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="da59b-112">napájení: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="da59b-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="da59b-113">Modulus: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="da59b-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="da59b-114">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="da59b-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="da59b-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="da59b-115">Remarks</span></span>

<span data-ttu-id="da59b-116">Doba trvá v poměru k počtu bitů v `power` , nikoli na `power` samotném.</span><span class="sxs-lookup"><span data-stu-id="da59b-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>