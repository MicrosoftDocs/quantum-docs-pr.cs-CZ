---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operace DrawRandomDouble
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708644"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="00949-102">Operace DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="00949-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="00949-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="00949-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="00949-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="00949-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="00949-105">Vykreslí náhodné reálné číslo v daném intervalu.</span><span class="sxs-lookup"><span data-stu-id="00949-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="00949-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="00949-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="00949-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="00949-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="00949-108">Nejmenší reálné číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="00949-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="00949-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="00949-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="00949-110">Největší reálné číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="00949-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="00949-111">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="00949-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="00949-112">Náhodné reálné číslo v intervalu zahrnujícím v rámci `min` `max` s jednotnou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="00949-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="00949-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="00949-113">Remarks</span></span>

<span data-ttu-id="00949-114">Dojde k chybě `max <= min` , pokud.</span><span class="sxs-lookup"><span data-stu-id="00949-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="00949-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="00949-115">See Also</span></span>

- [<span data-ttu-id="00949-116">Microsoft. ContinuousUniformDistribution.</span><span class="sxs-lookup"><span data-stu-id="00949-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)