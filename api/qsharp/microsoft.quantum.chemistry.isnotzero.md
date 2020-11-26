---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204058"
---
# <a name="isnotzero-function"></a><span data-ttu-id="c029f-102">IsNotZero – funkce</span><span class="sxs-lookup"><span data-stu-id="c029f-102">IsNotZero function</span></span>

<span data-ttu-id="c029f-103">Obor názvů: [Microsoft.. chemie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c029f-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="c029f-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c029f-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="c029f-105">Ověří, zda `Double` je číslo nepřibližně nula.</span><span class="sxs-lookup"><span data-stu-id="c029f-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="c029f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c029f-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="c029f-107">Number: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c029f-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c029f-108">Číslo, které se má zkontrolovat</span><span class="sxs-lookup"><span data-stu-id="c029f-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="c029f-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c029f-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c029f-110">Vrátí hodnotu true `number` , pokud má absolutní hodnotu větší než `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="c029f-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>