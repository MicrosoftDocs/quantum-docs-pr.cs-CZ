---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentI
title: ContinuedFractionConvergentI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentI
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: 2322e005a5afb73d9719eb65d9ebf50740f1c9fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708301"
---
# <a name="continuedfractionconvergenti-function"></a><span data-ttu-id="5ff38-102">ContinuedFractionConvergentI – funkce</span><span class="sxs-lookup"><span data-stu-id="5ff38-102">ContinuedFractionConvergentI function</span></span>

<span data-ttu-id="5ff38-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5ff38-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5ff38-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5ff38-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5ff38-105">Vyhledá pokračující zlomek Convergent nejbližší k `fraction` jmenovateli menší nebo rovno `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="5ff38-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentI (fraction : Microsoft.Quantum.Math.Fraction, denominatorBound : Int) : Microsoft.Quantum.Math.Fraction
```


## <a name="input"></a><span data-ttu-id="5ff38-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5ff38-106">Input</span></span>

### <a name="fraction--fraction"></a><span data-ttu-id="5ff38-107">zlomek: [zlomek](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="5ff38-107">fraction : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>




### <a name="denominatorbound--int"></a><span data-ttu-id="5ff38-108">denominatorBound: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5ff38-108">denominatorBound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--fraction"></a><span data-ttu-id="5ff38-109">Výstup: [zlomek](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="5ff38-109">Output : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>

<span data-ttu-id="5ff38-110">Pokračování zlomku nejbližšího k `fraction` jmenovateli je menší nebo rovno `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="5ff38-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>