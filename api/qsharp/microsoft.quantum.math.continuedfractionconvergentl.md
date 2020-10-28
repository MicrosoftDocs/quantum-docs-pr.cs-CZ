---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: ContinuedFractionConvergentL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: a02b38fedb5b0025f04e7bba86f2f998493206b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708577"
---
# <a name="continuedfractionconvergentl-function"></a><span data-ttu-id="a74dd-102">ContinuedFractionConvergentL – funkce</span><span class="sxs-lookup"><span data-stu-id="a74dd-102">ContinuedFractionConvergentL function</span></span>

<span data-ttu-id="a74dd-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a74dd-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a74dd-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a74dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a74dd-105">Vyhledá pokračující zlomek Convergent nejbližší k `fraction` jmenovateli menší nebo rovno `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="a74dd-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a><span data-ttu-id="a74dd-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a74dd-106">Input</span></span>

### <a name="fraction--bigfraction"></a><span data-ttu-id="a74dd-107">zlomek: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="a74dd-107">fraction : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>




### <a name="denominatorbound--bigint"></a><span data-ttu-id="a74dd-108">denominatorBound: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a74dd-108">denominatorBound : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigfraction"></a><span data-ttu-id="a74dd-109">Výstup: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="a74dd-109">Output : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>

<span data-ttu-id="a74dd-110">Pokračování zlomku nejbližšího k `fraction` jmenovateli je menší nebo rovno `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="a74dd-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>