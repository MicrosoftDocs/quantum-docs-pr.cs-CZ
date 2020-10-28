---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697232"
---
# <a name="inputencoder-function"></a><span data-ttu-id="2ba2c-102">InputEncoder – funkce</span><span class="sxs-lookup"><span data-stu-id="2ba2c-102">InputEncoder function</span></span>

<span data-ttu-id="2ba2c-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2ba2c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2ba2c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2ba2c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2ba2c-105">Vzhledem k sadě koeficientů a tolerance vrátí operaci přípravy stavu, která připraví každý koeficient jako odpovídající amplitudu výpočetního stavu.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="2ba2c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2ba2c-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="2ba2c-107">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="2ba2c-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="2ba2c-108">Koeficienty, které mají být zakódovány do vstupního stavu.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="2ba2c-109">Výstup: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="2ba2c-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="2ba2c-110">Operace přípravy stavu, která připraví dané koeficienty jako vstupní stav daného registru.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>