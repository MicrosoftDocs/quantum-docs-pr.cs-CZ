---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 5809b5463e6bf8ee73d095dfe4eafedfbb5e0702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852903"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="7485c-102">ArgComplexPolar – funkce</span><span class="sxs-lookup"><span data-stu-id="7485c-102">ArgComplexPolar function</span></span>

<span data-ttu-id="7485c-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7485c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7485c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7485c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7485c-105">Vrátí fázi komplexního čísla typu `ComplexPolar` .</span><span class="sxs-lookup"><span data-stu-id="7485c-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="7485c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7485c-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="7485c-107">vstup: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="7485c-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="7485c-108">Komplexní číslo $c = r e ^ {i t} $</span><span class="sxs-lookup"><span data-stu-id="7485c-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="7485c-109">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7485c-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7485c-110">Fáze $ \text{Arg} [c] = t $.</span><span class="sxs-lookup"><span data-stu-id="7485c-110">Phase $\text{Arg}[c] = t$.</span></span>