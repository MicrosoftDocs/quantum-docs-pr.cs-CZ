---
uid: Microsoft.Quantum.Arithmetic.IdenticalFormatFactFxP
title: IdenticalFormatFactFxP – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalFormatFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions and qubit numbers.
ms.openlocfilehash: e9fed13348583c8f403b733dea787b42856816c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843180"
---
# <a name="identicalformatfactfxp-function"></a><span data-ttu-id="a3f00-102">IdenticalFormatFactFxP – funkce</span><span class="sxs-lookup"><span data-stu-id="a3f00-102">IdenticalFormatFactFxP function</span></span>

<span data-ttu-id="a3f00-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a3f00-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a3f00-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="a3f00-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="a3f00-105">Vyhodnotit, že všechna čísla s pevnou desetinnou čárkou v zadaném poli mají stejné pozice bodů a qubit čísla.</span><span class="sxs-lookup"><span data-stu-id="a3f00-105">Assert that all fixed-point numbers in the provided array have identical point positions and qubit numbers.</span></span>

```qsharp
function IdenticalFormatFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a3f00-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a3f00-106">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="a3f00-107">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="a3f00-107">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="a3f00-108">Pole čísel s pevnou desetinnou čárkou, u kterých bude kontrolována kompatibilita (pomocí kontrolních výrazů).</span><span class="sxs-lookup"><span data-stu-id="a3f00-108">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="a3f00-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3f00-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

