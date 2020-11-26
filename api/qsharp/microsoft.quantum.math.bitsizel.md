---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 8b3d4cceb69619ed32977337fc0fe7401db38cbd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211045"
---
# <a name="bitsizel-function"></a><span data-ttu-id="c57a8-102">BitSizeL – funkce</span><span class="sxs-lookup"><span data-stu-id="c57a8-102">BitSizeL function</span></span>

<span data-ttu-id="c57a8-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c57a8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c57a8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c57a8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c57a8-105">Pro nezáporné celé číslo `a` vrátí počet bitů, které musí představovat `a` .</span><span class="sxs-lookup"><span data-stu-id="c57a8-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="c57a8-106">To znamená, že vrátí nejmenší $n $, který $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="c57a8-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="c57a8-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="c57a8-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c57a8-108">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c57a8-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c57a8-109">Celé číslo, jehož bitová velikost má být vypočítána.</span><span class="sxs-lookup"><span data-stu-id="c57a8-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="c57a8-110">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c57a8-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c57a8-111">Velikost bitové kopie `a` .</span><span class="sxs-lookup"><span data-stu-id="c57a8-111">The bit-size of `a`.</span></span>