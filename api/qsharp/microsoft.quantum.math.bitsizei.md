---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7cfe03908a8a394fc8ceb1c9facbf02f3db2d48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708307"
---
# <a name="bitsizei-function"></a><span data-ttu-id="b8bc4-102">BitSizeI – funkce</span><span class="sxs-lookup"><span data-stu-id="b8bc4-102">BitSizeI function</span></span>

<span data-ttu-id="b8bc4-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b8bc4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b8bc4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b8bc4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b8bc4-105">Pro nezáporné celé číslo `a` vrátí počet bitů, které musí představovat `a` .</span><span class="sxs-lookup"><span data-stu-id="b8bc4-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="b8bc4-106">To znamená, že vrátí nejmenší $n $, který $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="b8bc4-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="b8bc4-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="b8bc4-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="b8bc4-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b8bc4-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b8bc4-109">Celé číslo, jehož bitová velikost má být vypočítána.</span><span class="sxs-lookup"><span data-stu-id="b8bc4-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="b8bc4-110">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b8bc4-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b8bc4-111">Velikost bitové kopie `a` .</span><span class="sxs-lookup"><span data-stu-id="b8bc4-111">The bit-size of `a`.</span></span>