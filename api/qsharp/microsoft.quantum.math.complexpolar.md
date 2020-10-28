---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Uživatelem definovaný typ ComplexPolar
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697201"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="f24af-102">Uživatelem definovaný typ ComplexPolar</span><span class="sxs-lookup"><span data-stu-id="f24af-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="f24af-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f24af-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f24af-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f24af-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f24af-105">Představuje komplexní číslo v polárním tvaru.</span><span class="sxs-lookup"><span data-stu-id="f24af-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="f24af-106">Polární reprezentace komplexního čísla je $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="f24af-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="f24af-107">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="f24af-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="f24af-108">Velikost: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f24af-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f24af-109">Absolutní hodnota $r \ge $0 z $c $.</span><span class="sxs-lookup"><span data-stu-id="f24af-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="f24af-110">Argument: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f24af-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f24af-111">Fáze $t \in \mathbb R $ of $c $.</span><span class="sxs-lookup"><span data-stu-id="f24af-111">The phase $t \in \mathbb R$ of $c$.</span></span>