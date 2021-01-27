---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Uživatelem definovaný typ UnivariateOptimizationResult
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854569"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="777bf-102">Uživatelem definovaný typ UnivariateOptimizationResult</span><span class="sxs-lookup"><span data-stu-id="777bf-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="777bf-103">Obor názvů: [Microsoft.. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="777bf-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="777bf-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="777bf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="777bf-105">Představuje výsledek optimalizace funkce univariate.</span><span class="sxs-lookup"><span data-stu-id="777bf-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="777bf-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="777bf-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="777bf-107">Souřadnice: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="777bf-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="777bf-108">Vstup, při kterém byl nalezen optimální čas</span><span class="sxs-lookup"><span data-stu-id="777bf-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="777bf-109">Hodnota: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="777bf-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="777bf-110">Hodnota vrácená funkcí na optimálním místě.</span><span class="sxs-lookup"><span data-stu-id="777bf-110">Value returned by the function at its optimum.</span></span>