---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: e804e6a6ed82f14dcc9b8f721ad503d77922dc0f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194079"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="20e57-102">LocalUnivariateMinimum – funkce</span><span class="sxs-lookup"><span data-stu-id="20e57-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="20e57-103">Obor názvů: [Microsoft.. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="20e57-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="20e57-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="20e57-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="20e57-105">Vrátí místní minimum pro funkci univariate v rámci ohraničeného intervalu pomocí hledání zlatého intervalu.</span><span class="sxs-lookup"><span data-stu-id="20e57-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="20e57-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="20e57-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="20e57-107">FN: [Dvojitá](xref:microsoft.quantum.lang-ref.double) -> [Dvojitá přesnost](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="20e57-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="20e57-108">Funkce univariate, která se má minimalizovat</span><span class="sxs-lookup"><span data-stu-id="20e57-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="20e57-109">meze: ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="20e57-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="20e57-110">Interval, ve kterém má být nalezeno místní minimum.</span><span class="sxs-lookup"><span data-stu-id="20e57-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="20e57-111">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="20e57-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="20e57-112">Je možné, že se má tolerovat přesnost vstupu na funkci.</span><span class="sxs-lookup"><span data-stu-id="20e57-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="20e57-113">Hledání místních Optima bude pokračovat, dokud se interval nezmenší na šířku, než je tato tolerance.</span><span class="sxs-lookup"><span data-stu-id="20e57-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="20e57-114">Výstup: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="20e57-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="20e57-115">Místní Optima dané funkce, umístěný v rámci daných hranic.</span><span class="sxs-lookup"><span data-stu-id="20e57-115">A local optima of the given function, located within the given bounds.</span></span>