---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 2b84e92d08a3baad2552780cae91f447830cac82
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709159"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="19d9d-102">FastHadamardTransformed – funkce</span><span class="sxs-lookup"><span data-stu-id="19d9d-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="19d9d-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="19d9d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="19d9d-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="19d9d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="19d9d-105">Vypočítá Hadamard transformaci logické funkce v {-1,1} kódování pomocí metody Yates.</span><span class="sxs-lookup"><span data-stu-id="19d9d-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="19d9d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="19d9d-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="19d9d-107">Func: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="19d9d-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="19d9d-108">Tabulka pravdy v {-1,1} kódování</span><span class="sxs-lookup"><span data-stu-id="19d9d-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="19d9d-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="19d9d-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="19d9d-110">Spektrální koeficienty funkce</span><span class="sxs-lookup"><span data-stu-id="19d9d-110">Spectral coefficients of the function</span></span>