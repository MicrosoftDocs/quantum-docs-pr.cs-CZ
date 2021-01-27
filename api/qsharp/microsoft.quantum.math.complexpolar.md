---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Uživatelem definovaný typ ComplexPolar
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847351"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="0f9b5-102">Uživatelem definovaný typ ComplexPolar</span><span class="sxs-lookup"><span data-stu-id="0f9b5-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="0f9b5-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0f9b5-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0f9b5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f9b5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0f9b5-105">Představuje komplexní číslo v polárním tvaru.</span><span class="sxs-lookup"><span data-stu-id="0f9b5-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="0f9b5-106">Polární reprezentace komplexního čísla je $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="0f9b5-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="0f9b5-107">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="0f9b5-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="0f9b5-108">Velikost: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0f9b5-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0f9b5-109">Absolutní hodnota $r \ge $0 z $c $.</span><span class="sxs-lookup"><span data-stu-id="0f9b5-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="0f9b5-110">Argument: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0f9b5-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0f9b5-111">Fáze $t \in \mathbb R $ of $c $.</span><span class="sxs-lookup"><span data-stu-id="0f9b5-111">The phase $t \in \mathbb R$ of $c$.</span></span>