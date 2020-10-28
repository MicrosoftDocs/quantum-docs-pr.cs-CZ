---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
title: Uživatelem definovaný typ OptimizedBEGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEGeneratorSystem
qsharp.summary: Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.
ms.openlocfilehash: 06d13a8a64a3c572821ec97f8776d6f1dbe4a4ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698428"
---
# <a name="optimizedbegeneratorsystem-user-defined-type"></a><span data-ttu-id="7bd57-102">Uživatelem definovaný typ OptimizedBEGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="7bd57-102">OptimizedBEGeneratorSystem user defined type</span></span>

<span data-ttu-id="7bd57-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="7bd57-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="7bd57-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7bd57-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7bd57-105">Funkce, která vrací `OptimizedBETermIndex` data pro term s `n` daným celým `n` číslem, spolu s počtem podmínek v prvním `Int` a součtem absolutních hodnot všech výrazů v `Double` .</span><span class="sxs-lookup"><span data-stu-id="7bd57-105">Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.</span></span>

```qsharp

newtype OptimizedBEGeneratorSystem = (Int, Double, (Int -> Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex));
```

