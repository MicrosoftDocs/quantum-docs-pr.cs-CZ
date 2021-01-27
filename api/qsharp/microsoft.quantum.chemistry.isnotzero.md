---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839596"
---
# <a name="isnotzero-function"></a><span data-ttu-id="f767c-102">IsNotZero – funkce</span><span class="sxs-lookup"><span data-stu-id="f767c-102">IsNotZero function</span></span>

<span data-ttu-id="f767c-103">Obor názvů: [Microsoft.. chemie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f767c-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="f767c-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f767c-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="f767c-105">Ověří, zda `Double` je číslo nepřibližně nula.</span><span class="sxs-lookup"><span data-stu-id="f767c-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="f767c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f767c-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="f767c-107">Number: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f767c-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f767c-108">Číslo, které se má zkontrolovat</span><span class="sxs-lookup"><span data-stu-id="f767c-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="f767c-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f767c-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f767c-110">Vrátí hodnotu true `number` , pokud má absolutní hodnotu větší než `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="f767c-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>