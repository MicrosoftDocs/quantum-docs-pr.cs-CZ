---
uid: Microsoft.Quantum.Math.BigFraction
title: Uživatelem definovaný typ BigFraction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708313"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="b9efc-102">Uživatelem definovaný typ BigFraction</span><span class="sxs-lookup"><span data-stu-id="b9efc-102">BigFraction user defined type</span></span>

<span data-ttu-id="b9efc-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b9efc-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b9efc-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b9efc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b9efc-105">Představuje racionální číslo formuláře `p/q` .</span><span class="sxs-lookup"><span data-stu-id="b9efc-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="b9efc-106">Celé číslo `p` je první prvek řazené kolekce členů a `q` je druhým prvkem řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="b9efc-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="b9efc-107">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="b9efc-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="b9efc-108">Čitatel: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b9efc-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b9efc-109">Čitatel zlomku</span><span class="sxs-lookup"><span data-stu-id="b9efc-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="b9efc-110">Jmenovatel: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b9efc-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b9efc-111">Jmenovatel zlomku/</span><span class="sxs-lookup"><span data-stu-id="b9efc-111">Denominator of the fraction/</span></span>