---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: BoolAsResult – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: eea6c062afdbb3172e63261e52a82e2576c14011
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698328"
---
# <a name="boolasresult-function"></a><span data-ttu-id="115d4-102">BoolAsResult – funkce</span><span class="sxs-lookup"><span data-stu-id="115d4-102">BoolAsResult function</span></span>

<span data-ttu-id="115d4-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="115d4-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="115d4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="115d4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="115d4-105">Převede `Bool` typ na `Result` typ, kde `true` je mapován na `One` a `false` je mapován na `Zero` .</span><span class="sxs-lookup"><span data-stu-id="115d4-105">Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a><span data-ttu-id="115d4-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="115d4-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="115d4-107">vstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="115d4-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="115d4-108">`Bool` má být převedeno.</span><span class="sxs-lookup"><span data-stu-id="115d4-108">`Bool` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="115d4-109">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="115d4-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="115d4-110">`Result`Představuje `input` .</span><span class="sxs-lookup"><span data-stu-id="115d4-110">A `Result` representing the `input`.</span></span>