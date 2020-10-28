---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698681"
---
# <a name="isnotzero-function"></a><span data-ttu-id="c7b05-102">IsNotZero – funkce</span><span class="sxs-lookup"><span data-stu-id="c7b05-102">IsNotZero function</span></span>

<span data-ttu-id="c7b05-103">Obor názvů: [Microsoft.. chemie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c7b05-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="c7b05-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7b05-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7b05-105">Ověří, zda `Double` je číslo nepřibližně nula.</span><span class="sxs-lookup"><span data-stu-id="c7b05-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="c7b05-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c7b05-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="c7b05-107">Number: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c7b05-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c7b05-108">Číslo, které se má zkontrolovat</span><span class="sxs-lookup"><span data-stu-id="c7b05-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="c7b05-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c7b05-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c7b05-110">Vrátí hodnotu true `number` , pokud má absolutní hodnotu větší než `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="c7b05-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>