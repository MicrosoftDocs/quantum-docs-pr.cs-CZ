---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: 790551690cfba42df4cf7aa77e53e303050bdf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704089"
---
# <a name="isresultzero-function"></a><span data-ttu-id="4b50d-102">IsResultZero – funkce</span><span class="sxs-lookup"><span data-stu-id="4b50d-102">IsResultZero function</span></span>

<span data-ttu-id="4b50d-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4b50d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4b50d-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b50d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b50d-105">Testuje, zda je daná hodnota výsledku rovna `Zero` .</span><span class="sxs-lookup"><span data-stu-id="4b50d-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="4b50d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4b50d-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="4b50d-107">vstup: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="4b50d-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="4b50d-108">`Result` hodnota, která má být testována.</span><span class="sxs-lookup"><span data-stu-id="4b50d-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4b50d-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4b50d-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4b50d-110">Vrátí, `true` Pokud `input` je rovno `Zero` .</span><span class="sxs-lookup"><span data-stu-id="4b50d-110">Returns `true` if `input` is equal to `Zero`.</span></span>