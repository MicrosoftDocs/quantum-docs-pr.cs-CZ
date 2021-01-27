---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834190"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="9a404-102">BoolArrayAsResultArray – funkce</span><span class="sxs-lookup"><span data-stu-id="9a404-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="9a404-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="9a404-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="9a404-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a404-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a404-105">Převede `Bool[]` typ na `Result[]` typ, kde `true` je mapován na `One` a `false` je mapován na `Zero` .</span><span class="sxs-lookup"><span data-stu-id="9a404-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="9a404-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="9a404-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="9a404-107">vstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="9a404-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="9a404-108">`Bool[]` má být převedeno.</span><span class="sxs-lookup"><span data-stu-id="9a404-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="9a404-109">Výstup: __neplatný <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="9a404-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="9a404-110">`Result[]`Představuje `input` .</span><span class="sxs-lookup"><span data-stu-id="9a404-110">A `Result[]` representing the `input`.</span></span>