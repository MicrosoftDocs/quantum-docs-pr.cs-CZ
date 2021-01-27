---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 035c353c34362aa3486a7df9e7bb1bc95a6f63be
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856162"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="957e4-102">ApproximateInputEncoder – funkce</span><span class="sxs-lookup"><span data-stu-id="957e4-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="957e4-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="957e4-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="957e4-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="957e4-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="957e4-105">Vzhledem k množině koeficientů a tolerance vrátí operaci přípravy stavu, která připraví každý koeficient jako odpovídající amplitudu výpočetního stavu až po danou toleranci.</span><span class="sxs-lookup"><span data-stu-id="957e4-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="957e4-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="957e4-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="957e4-107">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="957e4-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="957e4-108">Tolerance aproximace, která se má použít při kódování daných koeficientů do vstupního stavu.</span><span class="sxs-lookup"><span data-stu-id="957e4-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="957e4-109">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="957e4-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="957e4-110">Koeficienty, které mají být zakódovány do vstupního stavu.</span><span class="sxs-lookup"><span data-stu-id="957e4-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="957e4-111">Výstup: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="957e4-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="957e4-112">Operace přípravy stavu, která připraví dané koeficienty jako vstupní stav daného registru.</span><span class="sxs-lookup"><span data-stu-id="957e4-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>