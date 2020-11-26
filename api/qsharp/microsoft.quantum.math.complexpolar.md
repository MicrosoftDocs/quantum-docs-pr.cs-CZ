---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Uživatelem definovaný typ ComplexPolar
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: a4f3a7b6ffa73271d7ac9674d8c718f6f09c0291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210977"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="1e3f1-102">Uživatelem definovaný typ ComplexPolar</span><span class="sxs-lookup"><span data-stu-id="1e3f1-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="1e3f1-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1e3f1-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1e3f1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e3f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e3f1-105">Představuje komplexní číslo v polárním tvaru.</span><span class="sxs-lookup"><span data-stu-id="1e3f1-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="1e3f1-106">Polární reprezentace komplexního čísla je $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="1e3f1-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="1e3f1-107">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="1e3f1-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="1e3f1-108">Velikost: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1e3f1-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1e3f1-109">Absolutní hodnota $r \ge $0 z $c $.</span><span class="sxs-lookup"><span data-stu-id="1e3f1-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="1e3f1-110">Argument: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1e3f1-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1e3f1-111">Fáze $t \in \mathbb R $ of $c $.</span><span class="sxs-lookup"><span data-stu-id="1e3f1-111">The phase $t \in \mathbb R$ of $c$.</span></span>