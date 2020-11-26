---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
title: Uživatelem definovaný typ OptimizedBEGeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEGeneratorSystem
qsharp.summary: Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.
ms.openlocfilehash: 438857b9e0d1bf43bbd4fdbc06ba7bf18c7871de
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224883"
---
# <a name="optimizedbegeneratorsystem-user-defined-type"></a><span data-ttu-id="9f3a5-102">Uživatelem definovaný typ OptimizedBEGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="9f3a5-102">OptimizedBEGeneratorSystem user defined type</span></span>

<span data-ttu-id="9f3a5-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="9f3a5-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="9f3a5-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9f3a5-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="9f3a5-105">Funkce, která vrací `OptimizedBETermIndex` data pro term s `n` daným celým `n` číslem, spolu s počtem podmínek v prvním `Int` a součtem absolutních hodnot všech výrazů v `Double` .</span><span class="sxs-lookup"><span data-stu-id="9f3a5-105">Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.</span></span>

```qsharp

newtype OptimizedBEGeneratorSystem = (Int, Double, (Int -> Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex));
```

