---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708337"
---
# <a name="argcomplex-function"></a><span data-ttu-id="eb010-102">ArgComplex – funkce</span><span class="sxs-lookup"><span data-stu-id="eb010-102">ArgComplex function</span></span>

<span data-ttu-id="eb010-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="eb010-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="eb010-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb010-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb010-105">Vrátí fázi komplexního čísla typu `Complex` .</span><span class="sxs-lookup"><span data-stu-id="eb010-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="eb010-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="eb010-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="eb010-107">vstup: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="eb010-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="eb010-108">Komplexní číslo $c = x + i y $.</span><span class="sxs-lookup"><span data-stu-id="eb010-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="eb010-109">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eb010-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eb010-110">Fáze $ \text{Arg} [c] = \text{ArcTan} (y, x) \in (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="eb010-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>