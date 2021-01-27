---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operace DrawRandomDouble
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847611"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="e5bd6-102">Operace DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="e5bd6-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="e5bd6-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="e5bd6-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="e5bd6-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e5bd6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e5bd6-105">Vykreslí náhodné reálné číslo v daném intervalu.</span><span class="sxs-lookup"><span data-stu-id="e5bd6-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="e5bd6-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e5bd6-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="e5bd6-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e5bd6-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e5bd6-108">Nejmenší reálné číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="e5bd6-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="e5bd6-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e5bd6-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e5bd6-110">Největší reálné číslo, které se má vykreslit.</span><span class="sxs-lookup"><span data-stu-id="e5bd6-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="e5bd6-111">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e5bd6-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e5bd6-112">Náhodné reálné číslo v intervalu zahrnujícím v rámci `min` `max` s jednotnou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="e5bd6-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="e5bd6-113">Příklad</span><span class="sxs-lookup"><span data-stu-id="e5bd6-113">Example</span></span>

<span data-ttu-id="e5bd6-114">Následující fragment Q # náhodně vykreslí úhel mezi $0 $ a $2 \pi $:</span><span class="sxs-lookup"><span data-stu-id="e5bd6-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a><span data-ttu-id="e5bd6-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e5bd6-115">Remarks</span></span>

<span data-ttu-id="e5bd6-116">Dojde k chybě `max <= min` , pokud.</span><span class="sxs-lookup"><span data-stu-id="e5bd6-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5bd6-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="e5bd6-117">See Also</span></span>

- [<span data-ttu-id="e5bd6-118">Microsoft. ContinuousUniformDistribution.</span><span class="sxs-lookup"><span data-stu-id="e5bd6-118">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)