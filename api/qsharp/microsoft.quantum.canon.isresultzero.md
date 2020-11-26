---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: b4e9b62b20e12a8dce544ce16dcddcf15fdf2680
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206523"
---
# <a name="isresultzero-function"></a><span data-ttu-id="d87e5-102">IsResultZero – funkce</span><span class="sxs-lookup"><span data-stu-id="d87e5-102">IsResultZero function</span></span>

<span data-ttu-id="d87e5-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d87e5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d87e5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d87e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d87e5-105">Testuje, zda je daná hodnota výsledku rovna `Zero` .</span><span class="sxs-lookup"><span data-stu-id="d87e5-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="d87e5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d87e5-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="d87e5-107">vstup: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="d87e5-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="d87e5-108">`Result` hodnota, která má být testována.</span><span class="sxs-lookup"><span data-stu-id="d87e5-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d87e5-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d87e5-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d87e5-110">Vrátí, `true` Pokud `input` je rovno `Zero` .</span><span class="sxs-lookup"><span data-stu-id="d87e5-110">Returns `true` if `input` is equal to `Zero`.</span></span>