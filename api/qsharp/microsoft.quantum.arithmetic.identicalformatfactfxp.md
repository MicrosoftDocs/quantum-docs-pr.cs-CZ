---
uid: Microsoft.Quantum.Arithmetic.IdenticalFormatFactFxP
title: IdenticalFormatFactFxP – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalFormatFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions and qubit numbers.
ms.openlocfilehash: d19e29d4786a728c2105dc55673c49b2885176f8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223030"
---
# <a name="identicalformatfactfxp-function"></a><span data-ttu-id="eb85b-102">IdenticalFormatFactFxP – funkce</span><span class="sxs-lookup"><span data-stu-id="eb85b-102">IdenticalFormatFactFxP function</span></span>

<span data-ttu-id="eb85b-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="eb85b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="eb85b-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="eb85b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="eb85b-105">Vyhodnotit, že všechna čísla s pevnou desetinnou čárkou v zadaném poli mají stejné pozice bodů a qubit čísla.</span><span class="sxs-lookup"><span data-stu-id="eb85b-105">Assert that all fixed-point numbers in the provided array have identical point positions and qubit numbers.</span></span>

```qsharp
function IdenticalFormatFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="eb85b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="eb85b-106">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="eb85b-107">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="eb85b-107">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="eb85b-108">Pole čísel s pevnou desetinnou čárkou, u kterých bude kontrolována kompatibilita (pomocí kontrolních výrazů).</span><span class="sxs-lookup"><span data-stu-id="eb85b-108">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb85b-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb85b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

