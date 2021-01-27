---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operace DrawRandomBool
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853694"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="31be1-102">Operace DrawRandomBool</span><span class="sxs-lookup"><span data-stu-id="31be1-102">DrawRandomBool operation</span></span>

<span data-ttu-id="31be1-103">Obor názvů: [Microsoft. Prohodile](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="31be1-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="31be1-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="31be1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="31be1-105">S ohledem na pravděpodobnost úspěchu vrátí jednu Bernoulliho zkušební verzi, která je pravdivá s danou pravděpodobností.</span><span class="sxs-lookup"><span data-stu-id="31be1-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="31be1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="31be1-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="31be1-107">successProbability: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="31be1-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="31be1-108">Pravděpodobnost, se kterou `true` by měla být vrácena.</span><span class="sxs-lookup"><span data-stu-id="31be1-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="31be1-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="31be1-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="31be1-110">`true` s pravděpodobností `successProbability` a `false` s pravděpodobností `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="31be1-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>

## <a name="example"></a><span data-ttu-id="31be1-111">Příklad</span><span class="sxs-lookup"><span data-stu-id="31be1-111">Example</span></span>

<span data-ttu-id="31be1-112">Následující ukázky fragmentů kódu Q # přejdou z posunuté mince:</span><span class="sxs-lookup"><span data-stu-id="31be1-112">The following Q# snippet samples flips from a biased coin:</span></span>

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```