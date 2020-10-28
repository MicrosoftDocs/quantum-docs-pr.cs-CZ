---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Uživatelem definovaný typ MCMTMask
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 0d3ca12d55fa4b5e8332d50939954de29e39b715
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709292"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="31800-102">Uživatelem definovaný typ MCMTMask</span><span class="sxs-lookup"><span data-stu-id="31800-102">MCMTMask user defined type</span></span>

<span data-ttu-id="31800-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="31800-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="31800-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31800-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31800-105">Typ představující vícenásobnou Toffoli bránu s více cíli.</span><span class="sxs-lookup"><span data-stu-id="31800-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="31800-106">První celé číslo je bitovou maskou pro řídicí čáry.</span><span class="sxs-lookup"><span data-stu-id="31800-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="31800-107">Bitové indexy, které jsou nastaveny, odpovídají indexům řídicích čar.</span><span class="sxs-lookup"><span data-stu-id="31800-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="31800-108">Druhé celé číslo je Bitová maska pro cílové řádky.</span><span class="sxs-lookup"><span data-stu-id="31800-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="31800-109">Bitové indexy, které jsou nastaveny, odpovídají cílovým indexům řádků.</span><span class="sxs-lookup"><span data-stu-id="31800-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="31800-110">Bitové indexy obou celých čísel musí být nesouvislé.</span><span class="sxs-lookup"><span data-stu-id="31800-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="31800-111">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="31800-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="31800-112">ControlMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="31800-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="31800-113">TargetMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="31800-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

