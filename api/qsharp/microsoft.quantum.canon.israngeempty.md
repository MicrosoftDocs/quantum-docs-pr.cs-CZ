---
uid: Microsoft.Quantum.Canon.IsRangeEmpty
title: IsRangeEmpty – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsRangeEmpty
qsharp.summary: Returns true if and only if input range is empty.
ms.openlocfilehash: 029de3ca81002bd0e460135bb8e70e92019588ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206591"
---
# <a name="israngeempty-function"></a><span data-ttu-id="8336a-102">IsRangeEmpty – funkce</span><span class="sxs-lookup"><span data-stu-id="8336a-102">IsRangeEmpty function</span></span>

<span data-ttu-id="8336a-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8336a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8336a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8336a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8336a-105">Vrátí hodnotu true pouze v případě, že je vstupní rozsah prázdný.</span><span class="sxs-lookup"><span data-stu-id="8336a-105">Returns true if and only if input range is empty.</span></span>

```qsharp
function IsRangeEmpty (rng : Range) : Bool
```


## <a name="input"></a><span data-ttu-id="8336a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8336a-106">Input</span></span>

### <a name="rng--range"></a><span data-ttu-id="8336a-107">RNG: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="8336a-107">rng : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="8336a-108">Libovolný rozsah</span><span class="sxs-lookup"><span data-stu-id="8336a-108">Any range</span></span>



## <a name="output--bool"></a><span data-ttu-id="8336a-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8336a-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8336a-110">True, pokud je a jenom pokud `rng` je prázdný</span><span class="sxs-lookup"><span data-stu-id="8336a-110">True, if and only if `rng` is empty</span></span>