---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 97068f12050317a9aa17c95f33650ef6f406066d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708302"
---
# <a name="bitsizel-function"></a><span data-ttu-id="99689-102">BitSizeL – funkce</span><span class="sxs-lookup"><span data-stu-id="99689-102">BitSizeL function</span></span>

<span data-ttu-id="99689-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="99689-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="99689-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99689-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="99689-105">Pro nezáporné celé číslo `a` vrátí počet bitů, které musí představovat `a` .</span><span class="sxs-lookup"><span data-stu-id="99689-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="99689-106">To znamená, že vrátí nejmenší $n $, který $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="99689-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="99689-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="99689-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="99689-108">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="99689-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="99689-109">Celé číslo, jehož bitová velikost má být vypočítána.</span><span class="sxs-lookup"><span data-stu-id="99689-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="99689-110">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99689-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="99689-111">Velikost bitové kopie `a` .</span><span class="sxs-lookup"><span data-stu-id="99689-111">The bit-size of `a`.</span></span>