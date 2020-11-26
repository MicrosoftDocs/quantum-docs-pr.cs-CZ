---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Uživatelem definovaný typ MCMTMask
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 3c2debbb1f2019c7188dcb00f8ac09154fd4fd4f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203009"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="a94e6-102">Uživatelem definovaný typ MCMTMask</span><span class="sxs-lookup"><span data-stu-id="a94e6-102">MCMTMask user defined type</span></span>

<span data-ttu-id="a94e6-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a94e6-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a94e6-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a94e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a94e6-105">Typ představující vícenásobnou Toffoli bránu s více cíli.</span><span class="sxs-lookup"><span data-stu-id="a94e6-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="a94e6-106">První celé číslo je bitovou maskou pro řídicí čáry.</span><span class="sxs-lookup"><span data-stu-id="a94e6-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="a94e6-107">Bitové indexy, které jsou nastaveny, odpovídají indexům řídicích čar.</span><span class="sxs-lookup"><span data-stu-id="a94e6-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="a94e6-108">Druhé celé číslo je Bitová maska pro cílové řádky.</span><span class="sxs-lookup"><span data-stu-id="a94e6-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="a94e6-109">Bitové indexy, které jsou nastaveny, odpovídají cílovým indexům řádků.</span><span class="sxs-lookup"><span data-stu-id="a94e6-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="a94e6-110">Bitové indexy obou celých čísel musí být nesouvislé.</span><span class="sxs-lookup"><span data-stu-id="a94e6-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="a94e6-111">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="a94e6-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="a94e6-112">ControlMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a94e6-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="a94e6-113">TargetMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a94e6-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

