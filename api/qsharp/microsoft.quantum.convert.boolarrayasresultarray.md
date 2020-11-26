---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 388fb67ba33810fc813fb646577bfa7f4a2b51ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224458"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="9f1dd-102">BoolArrayAsResultArray – funkce</span><span class="sxs-lookup"><span data-stu-id="9f1dd-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="9f1dd-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="9f1dd-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="9f1dd-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9f1dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9f1dd-105">Převede `Bool[]` typ na `Result[]` typ, kde `true` je mapován na `One` a `false` je mapován na `Zero` .</span><span class="sxs-lookup"><span data-stu-id="9f1dd-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="9f1dd-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="9f1dd-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="9f1dd-107">vstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="9f1dd-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="9f1dd-108">`Bool[]` má být převedeno.</span><span class="sxs-lookup"><span data-stu-id="9f1dd-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="9f1dd-109">Výstup: __neplatný <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="9f1dd-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="9f1dd-110">`Result[]`Představuje `input` .</span><span class="sxs-lookup"><span data-stu-id="9f1dd-110">A `Result[]` representing the `input`.</span></span>