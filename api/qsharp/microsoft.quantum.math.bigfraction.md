---
uid: Microsoft.Quantum.Math.BigFraction
title: Uživatelem definovaný typ BigFraction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211079"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="aa59c-102">Uživatelem definovaný typ BigFraction</span><span class="sxs-lookup"><span data-stu-id="aa59c-102">BigFraction user defined type</span></span>

<span data-ttu-id="aa59c-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="aa59c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="aa59c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa59c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa59c-105">Představuje racionální číslo formuláře `p/q` .</span><span class="sxs-lookup"><span data-stu-id="aa59c-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="aa59c-106">Celé číslo `p` je první prvek řazené kolekce členů a `q` je druhým prvkem řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="aa59c-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="aa59c-107">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="aa59c-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="aa59c-108">Čitatel: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="aa59c-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="aa59c-109">Čitatel zlomku</span><span class="sxs-lookup"><span data-stu-id="aa59c-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="aa59c-110">Jmenovatel: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="aa59c-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="aa59c-111">Jmenovatel zlomku/</span><span class="sxs-lookup"><span data-stu-id="aa59c-111">Denominator of the fraction/</span></span>