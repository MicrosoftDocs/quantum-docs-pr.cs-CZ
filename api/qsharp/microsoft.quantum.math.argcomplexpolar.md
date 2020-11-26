---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 7088397bd60e2779ef60afc1bb7108d937a62c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195762"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="50086-102">ArgComplexPolar – funkce</span><span class="sxs-lookup"><span data-stu-id="50086-102">ArgComplexPolar function</span></span>

<span data-ttu-id="50086-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="50086-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="50086-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="50086-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="50086-105">Vrátí fázi komplexního čísla typu `ComplexPolar` .</span><span class="sxs-lookup"><span data-stu-id="50086-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="50086-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="50086-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="50086-107">vstup: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="50086-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="50086-108">Komplexní číslo $c = r e ^ {i t} $</span><span class="sxs-lookup"><span data-stu-id="50086-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="50086-109">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="50086-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="50086-110">Fáze $ \text{Arg} [c] = t $.</span><span class="sxs-lookup"><span data-stu-id="50086-110">Phase $\text{Arg}[c] = t$.</span></span>