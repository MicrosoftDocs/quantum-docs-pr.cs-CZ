---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: BoolAsResult – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 0190529dd804922a69499fbf1c2c4c916c4b720a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214241"
---
# <a name="boolasresult-function"></a><span data-ttu-id="dca0b-102">BoolAsResult – funkce</span><span class="sxs-lookup"><span data-stu-id="dca0b-102">BoolAsResult function</span></span>

<span data-ttu-id="dca0b-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="dca0b-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="dca0b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dca0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dca0b-105">Převede `Bool` typ na `Result` typ, kde `true` je mapován na `One` a `false` je mapován na `Zero` .</span><span class="sxs-lookup"><span data-stu-id="dca0b-105">Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a><span data-ttu-id="dca0b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="dca0b-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="dca0b-107">vstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dca0b-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dca0b-108">`Bool` má být převedeno.</span><span class="sxs-lookup"><span data-stu-id="dca0b-108">`Bool` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="dca0b-109">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="dca0b-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="dca0b-110">`Result`Představuje `input` .</span><span class="sxs-lookup"><span data-stu-id="dca0b-110">A `Result` representing the `input`.</span></span>