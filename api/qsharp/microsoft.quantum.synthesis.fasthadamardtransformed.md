---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203089"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="6f638-102">FastHadamardTransformed – funkce</span><span class="sxs-lookup"><span data-stu-id="6f638-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="6f638-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6f638-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6f638-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f638-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f638-105">Vypočítá Hadamard transformaci logické funkce v {-1,1} kódování pomocí metody Yates.</span><span class="sxs-lookup"><span data-stu-id="6f638-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="6f638-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6f638-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="6f638-107">Func: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6f638-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6f638-108">Tabulka pravdy v {-1,1} kódování</span><span class="sxs-lookup"><span data-stu-id="6f638-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="6f638-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6f638-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6f638-110">Spektrální koeficienty funkce</span><span class="sxs-lookup"><span data-stu-id="6f638-110">Spectral coefficients of the function</span></span>