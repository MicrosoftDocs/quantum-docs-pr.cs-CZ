---
uid: Microsoft.Quantum.Math.AbsComplexPolar
title: AbsComplexPolar – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplexPolar
qsharp.summary: Returns the absolute value of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 01845556cbabde768f9c7c47c733453048df9416
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195983"
---
# <a name="abscomplexpolar-function"></a><span data-ttu-id="3d2aa-102">AbsComplexPolar – funkce</span><span class="sxs-lookup"><span data-stu-id="3d2aa-102">AbsComplexPolar function</span></span>

<span data-ttu-id="3d2aa-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="3d2aa-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="3d2aa-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3d2aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3d2aa-105">Vrátí absolutní hodnotu komplexního čísla typu `ComplexPolar` .</span><span class="sxs-lookup"><span data-stu-id="3d2aa-105">Returns the absolute value of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function AbsComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="3d2aa-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3d2aa-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="3d2aa-107">vstup: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="3d2aa-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="3d2aa-108">Komplexní číslo $c = r e ^ {i t} $</span><span class="sxs-lookup"><span data-stu-id="3d2aa-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="3d2aa-109">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3d2aa-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3d2aa-110">Absolutní hodnota $ | c | = r $.</span><span class="sxs-lookup"><span data-stu-id="3d2aa-110">Absolute value $|c| = r$.</span></span>