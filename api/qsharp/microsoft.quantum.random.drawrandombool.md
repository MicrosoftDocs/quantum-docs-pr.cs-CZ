---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operace DrawRandomBool
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706713"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="80a06-102">Operace DrawRandomBool</span><span class="sxs-lookup"><span data-stu-id="80a06-102">DrawRandomBool operation</span></span>

<span data-ttu-id="80a06-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="80a06-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="80a06-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80a06-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="80a06-105">S ohledem na pravděpodobnost úspěchu vrátí jednu Bernoulliho zkušební verzi, která je pravdivá s danou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="80a06-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="80a06-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="80a06-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="80a06-107">successProbability: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="80a06-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="80a06-108">Pravděpodobnost, se kterou `true` by měla být vrácena.</span><span class="sxs-lookup"><span data-stu-id="80a06-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="80a06-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="80a06-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="80a06-110">`true` s pravděpodobností `successProbability` a `false` s pravděpodobností `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="80a06-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>