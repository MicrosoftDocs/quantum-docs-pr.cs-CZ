---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: ContinuedFractionConvergentL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: 14f0eee5565b3e80f4090a2d3763ef96c928368d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856390"
---
# <a name="continuedfractionconvergentl-function"></a><span data-ttu-id="c3b07-102">ContinuedFractionConvergentL – funkce</span><span class="sxs-lookup"><span data-stu-id="c3b07-102">ContinuedFractionConvergentL function</span></span>

<span data-ttu-id="c3b07-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c3b07-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c3b07-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3b07-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3b07-105">Vyhledá pokračující zlomek Convergent nejbližší k `fraction` jmenovateli menší nebo rovno `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="c3b07-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a><span data-ttu-id="c3b07-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c3b07-106">Input</span></span>

### <a name="fraction--bigfraction"></a><span data-ttu-id="c3b07-107">zlomek: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="c3b07-107">fraction : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>




### <a name="denominatorbound--bigint"></a><span data-ttu-id="c3b07-108">denominatorBound: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c3b07-108">denominatorBound : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigfraction"></a><span data-ttu-id="c3b07-109">Výstup: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="c3b07-109">Output : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>

<span data-ttu-id="c3b07-110">Pokračování zlomku nejbližšího k `fraction` jmenovateli je menší nebo rovno `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="c3b07-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>