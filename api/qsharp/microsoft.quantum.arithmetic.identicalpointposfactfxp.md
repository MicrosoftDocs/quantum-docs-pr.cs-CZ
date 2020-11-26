---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 907e270e1c3710fb346044ad7757171c6d5f568d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223047"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="2b78d-102">IdenticalPointPosFactFxP – funkce</span><span class="sxs-lookup"><span data-stu-id="2b78d-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="2b78d-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2b78d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2b78d-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="2b78d-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="2b78d-105">Vyhodnotit, že všechna čísla s pevnou desetinnou čárkou v zadaném poli mají stejné pozice bodů při počítání z nejméně významného bitu.</span><span class="sxs-lookup"><span data-stu-id="2b78d-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="2b78d-106">To znamená, že počet bitů minus pozice bodu musí být konstantní pro všechna čísla s pevnou desetinnou čárkou v poli.</span><span class="sxs-lookup"><span data-stu-id="2b78d-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2b78d-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="2b78d-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="2b78d-108">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="2b78d-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="2b78d-109">Pole čísel s pevnou desetinnou čárkou, u kterých bude kontrolována kompatibilita (pomocí kontrolních výrazů).</span><span class="sxs-lookup"><span data-stu-id="2b78d-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b78d-110">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b78d-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

