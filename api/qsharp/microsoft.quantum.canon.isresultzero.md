---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: b1e7cf6324a2a90f10b6aa93811f2df60fe3afbd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840316"
---
# <a name="isresultzero-function"></a><span data-ttu-id="4f9d3-102">IsResultZero – funkce</span><span class="sxs-lookup"><span data-stu-id="4f9d3-102">IsResultZero function</span></span>

<span data-ttu-id="4f9d3-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4f9d3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4f9d3-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f9d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f9d3-105">Testuje, zda je daná hodnota výsledku rovna `Zero` .</span><span class="sxs-lookup"><span data-stu-id="4f9d3-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="4f9d3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4f9d3-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="4f9d3-107">vstup: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="4f9d3-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="4f9d3-108">`Result` hodnota, která má být testována.</span><span class="sxs-lookup"><span data-stu-id="4f9d3-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4f9d3-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4f9d3-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4f9d3-110">Vrátí, `true` Pokud `input` je rovno `Zero` .</span><span class="sxs-lookup"><span data-stu-id="4f9d3-110">Returns `true` if `input` is equal to `Zero`.</span></span>