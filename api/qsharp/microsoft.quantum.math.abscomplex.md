---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: 2bb4caa140bef36d893da834eac1c94b8dd8b0e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846074"
---
# <a name="abscomplex-function"></a><span data-ttu-id="b8347-102">AbsComplex – funkce</span><span class="sxs-lookup"><span data-stu-id="b8347-102">AbsComplex function</span></span>

<span data-ttu-id="b8347-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b8347-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b8347-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b8347-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b8347-105">Vrátí absolutní hodnotu komplexního čísla typu `Complex` .</span><span class="sxs-lookup"><span data-stu-id="b8347-105">Returns the absolute value of a complex number of type `Complex`.</span></span>

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="b8347-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b8347-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="b8347-107">vstup: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="b8347-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="b8347-108">Komplexní číslo $c = x + i y $.</span><span class="sxs-lookup"><span data-stu-id="b8347-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="b8347-109">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b8347-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b8347-110">Absolutní hodnota $ | c | = \sqrt{x ^ 2 + y ^ 2} $.</span><span class="sxs-lookup"><span data-stu-id="b8347-110">Absolute value $|c| = \sqrt{x^2 + y^2}$.</span></span>