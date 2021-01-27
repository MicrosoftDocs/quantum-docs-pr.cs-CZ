---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: ed70d9f24af06f8918083307c98a5f6c4671f1c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852944"
---
# <a name="inputencoder-function"></a><span data-ttu-id="66e65-102">InputEncoder – funkce</span><span class="sxs-lookup"><span data-stu-id="66e65-102">InputEncoder function</span></span>

<span data-ttu-id="66e65-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="66e65-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="66e65-104">Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="66e65-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="66e65-105">Vzhledem k sadě koeficientů a tolerance vrátí operaci přípravy stavu, která připraví každý koeficient jako odpovídající amplitudu výpočetního stavu.</span><span class="sxs-lookup"><span data-stu-id="66e65-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="66e65-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="66e65-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="66e65-107">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="66e65-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="66e65-108">Koeficienty, které mají být zakódovány do vstupního stavu.</span><span class="sxs-lookup"><span data-stu-id="66e65-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="66e65-109">Výstup: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="66e65-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="66e65-110">Operace přípravy stavu, která připraví dané koeficienty jako vstupní stav daného registru.</span><span class="sxs-lookup"><span data-stu-id="66e65-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>