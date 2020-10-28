---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: fa8845fd92e5c16b4ff15436caf42df4f1e151cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704104"
---
# <a name="isresultone-function"></a><span data-ttu-id="43bc0-102">IsResultOne – funkce</span><span class="sxs-lookup"><span data-stu-id="43bc0-102">IsResultOne function</span></span>

<span data-ttu-id="43bc0-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="43bc0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="43bc0-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="43bc0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="43bc0-105">Testuje, zda je daná hodnota výsledku rovna `One` .</span><span class="sxs-lookup"><span data-stu-id="43bc0-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="43bc0-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="43bc0-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="43bc0-107">vstup: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="43bc0-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="43bc0-108">`Result` hodnota, která má být testována.</span><span class="sxs-lookup"><span data-stu-id="43bc0-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="43bc0-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="43bc0-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="43bc0-110">Vrátí, `true` Pokud `input` je rovno `One` .</span><span class="sxs-lookup"><span data-stu-id="43bc0-110">Returns `true` if `input` is equal to `One`.</span></span>