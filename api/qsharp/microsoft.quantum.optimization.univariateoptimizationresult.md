---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Uživatelem definovaný typ UnivariateOptimizationResult
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708788"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="59c01-102">Uživatelem definovaný typ UnivariateOptimizationResult</span><span class="sxs-lookup"><span data-stu-id="59c01-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="59c01-103">Obor názvů: [Microsoft.. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="59c01-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="59c01-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="59c01-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="59c01-105">Představuje výsledek optimalizace funkce univariate.</span><span class="sxs-lookup"><span data-stu-id="59c01-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="59c01-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="59c01-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="59c01-107">Souřadnice: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="59c01-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="59c01-108">Vstup, při kterém byl nalezen optimální čas</span><span class="sxs-lookup"><span data-stu-id="59c01-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="59c01-109">Hodnota: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="59c01-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="59c01-110">Hodnota vrácená funkcí na optimálním místě.</span><span class="sxs-lookup"><span data-stu-id="59c01-110">Value returned by the function at its optimum.</span></span>