---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: ResultArrayAsBoolArray – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 384531137474562ebc8cc24dcd1ac976dc91ad9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832598"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="4da2a-102">ResultArrayAsBoolArray – funkce</span><span class="sxs-lookup"><span data-stu-id="4da2a-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="4da2a-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="4da2a-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="4da2a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4da2a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4da2a-105">Převede `Result[]` typ na `Bool[]` typ, kde `One` je mapován na `true` a `Zero` je mapován na `false` .</span><span class="sxs-lookup"><span data-stu-id="4da2a-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="4da2a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4da2a-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="4da2a-107">vstup: __neplatný <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="4da2a-107">input : __invalid<Result>__[]</span></span>

<span data-ttu-id="4da2a-108">`Result[]` má být převedeno.</span><span class="sxs-lookup"><span data-stu-id="4da2a-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4da2a-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="4da2a-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="4da2a-110">`Bool[]`Představuje `input` .</span><span class="sxs-lookup"><span data-stu-id="4da2a-110">A `Bool[]` representing the `input`.</span></span>