---
uid: Microsoft.Quantum.Math.Fraction
title: Typ zlomku uživatelsky definovaného typu
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708505"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="1a168-102">Typ zlomku uživatelsky definovaného typu</span><span class="sxs-lookup"><span data-stu-id="1a168-102">Fraction user defined type</span></span>

<span data-ttu-id="1a168-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1a168-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1a168-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1a168-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1a168-105">Představuje racionální číslo formuláře `p/q` .</span><span class="sxs-lookup"><span data-stu-id="1a168-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="1a168-106">Celé číslo `p` je první prvek řazené kolekce členů a `q` je druhým prvkem řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="1a168-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="1a168-107">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="1a168-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="1a168-108">Čitatel: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1a168-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1a168-109">Čitatel zlomku</span><span class="sxs-lookup"><span data-stu-id="1a168-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="1a168-110">Jmenovatel: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1a168-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1a168-111">Jmenovatel zlomku/</span><span class="sxs-lookup"><span data-stu-id="1a168-111">Denominator of the fraction/</span></span>