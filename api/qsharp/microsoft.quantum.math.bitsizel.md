---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: c94d873d7117fd2ee66226fab6d4bfc5b33bc46d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848914"
---
# <a name="bitsizel-function"></a><span data-ttu-id="a3041-102">BitSizeL – funkce</span><span class="sxs-lookup"><span data-stu-id="a3041-102">BitSizeL function</span></span>

<span data-ttu-id="a3041-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a3041-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a3041-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3041-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3041-105">Pro nezáporné celé číslo `a` vrátí počet bitů, které musí představovat `a` .</span><span class="sxs-lookup"><span data-stu-id="a3041-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="a3041-106">To znamená, že vrátí nejmenší $n $, který $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="a3041-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="a3041-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="a3041-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="a3041-108">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a3041-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a3041-109">Celé číslo, jehož bitová velikost má být vypočítána.</span><span class="sxs-lookup"><span data-stu-id="a3041-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="a3041-110">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a3041-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a3041-111">Velikost bitové kopie `a` .</span><span class="sxs-lookup"><span data-stu-id="a3041-111">The bit-size of `a`.</span></span>