---
uid: Microsoft.Quantum.Math.Fraction
title: Typ zlomku uživatelsky definovaného typu
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210671"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="a45be-102">Typ zlomku uživatelsky definovaného typu</span><span class="sxs-lookup"><span data-stu-id="a45be-102">Fraction user defined type</span></span>

<span data-ttu-id="a45be-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a45be-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a45be-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a45be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a45be-105">Představuje racionální číslo formuláře `p/q` .</span><span class="sxs-lookup"><span data-stu-id="a45be-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="a45be-106">Celé číslo `p` je první prvek řazené kolekce členů a `q` je druhým prvkem řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="a45be-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="a45be-107">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="a45be-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="a45be-108">Čitatel: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a45be-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a45be-109">Čitatel zlomku</span><span class="sxs-lookup"><span data-stu-id="a45be-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="a45be-110">Jmenovatel: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a45be-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a45be-111">Jmenovatel zlomku/</span><span class="sxs-lookup"><span data-stu-id="a45be-111">Denominator of the fraction/</span></span>