---
uid: Microsoft.Quantum.Math.Fraction
title: Typ zlomku uživatelsky definovaného typu
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857521"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="ae332-102">Typ zlomku uživatelsky definovaného typu</span><span class="sxs-lookup"><span data-stu-id="ae332-102">Fraction user defined type</span></span>

<span data-ttu-id="ae332-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ae332-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ae332-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae332-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae332-105">Představuje racionální číslo formuláře `p/q` .</span><span class="sxs-lookup"><span data-stu-id="ae332-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="ae332-106">Celé číslo `p` je první prvek řazené kolekce členů a `q` je druhým prvkem řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="ae332-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="ae332-107">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="ae332-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="ae332-108">Čitatel: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ae332-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ae332-109">Čitatel zlomku</span><span class="sxs-lookup"><span data-stu-id="ae332-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="ae332-110">Jmenovatel: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ae332-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ae332-111">Jmenovatel zlomku/</span><span class="sxs-lookup"><span data-stu-id="ae332-111">Denominator of the fraction/</span></span>