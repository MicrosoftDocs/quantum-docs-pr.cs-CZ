---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Uživatelem definovaný typ UnivariateOptimizationResult
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194028"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="b755b-102">Uživatelem definovaný typ UnivariateOptimizationResult</span><span class="sxs-lookup"><span data-stu-id="b755b-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="b755b-103">Obor názvů: [Microsoft.. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="b755b-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="b755b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b755b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b755b-105">Představuje výsledek optimalizace funkce univariate.</span><span class="sxs-lookup"><span data-stu-id="b755b-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="b755b-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="b755b-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="b755b-107">Souřadnice: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b755b-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b755b-108">Vstup, při kterém byl nalezen optimální čas</span><span class="sxs-lookup"><span data-stu-id="b755b-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="b755b-109">Hodnota: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b755b-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b755b-110">Hodnota vrácená funkcí na optimálním místě.</span><span class="sxs-lookup"><span data-stu-id="b755b-110">Value returned by the function at its optimum.</span></span>