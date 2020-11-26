---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: eb4116b60bb415465375e374ad84e990135c231c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206540"
---
# <a name="isresultone-function"></a><span data-ttu-id="e0ffa-102">IsResultOne – funkce</span><span class="sxs-lookup"><span data-stu-id="e0ffa-102">IsResultOne function</span></span>

<span data-ttu-id="e0ffa-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e0ffa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e0ffa-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0ffa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0ffa-105">Testuje, zda je daná hodnota výsledku rovna `One` .</span><span class="sxs-lookup"><span data-stu-id="e0ffa-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="e0ffa-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e0ffa-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="e0ffa-107">vstup: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="e0ffa-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="e0ffa-108">`Result` hodnota, která má být testována.</span><span class="sxs-lookup"><span data-stu-id="e0ffa-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e0ffa-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e0ffa-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e0ffa-110">Vrátí, `true` Pokud `input` je rovno `One` .</span><span class="sxs-lookup"><span data-stu-id="e0ffa-110">Returns `true` if `input` is equal to `One`.</span></span>