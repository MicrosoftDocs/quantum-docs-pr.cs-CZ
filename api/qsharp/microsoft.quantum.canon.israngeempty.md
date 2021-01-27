---
uid: Microsoft.Quantum.Canon.IsRangeEmpty
title: IsRangeEmpty – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsRangeEmpty
qsharp.summary: Returns true if and only if input range is empty.
ms.openlocfilehash: a36d174bd0e89df0f546290fc469214fd820aa5c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840337"
---
# <a name="israngeempty-function"></a><span data-ttu-id="d2c78-102">IsRangeEmpty – funkce</span><span class="sxs-lookup"><span data-stu-id="d2c78-102">IsRangeEmpty function</span></span>

<span data-ttu-id="d2c78-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d2c78-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d2c78-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2c78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2c78-105">Vrátí hodnotu true pouze v případě, že je vstupní rozsah prázdný.</span><span class="sxs-lookup"><span data-stu-id="d2c78-105">Returns true if and only if input range is empty.</span></span>

```qsharp
function IsRangeEmpty (rng : Range) : Bool
```


## <a name="input"></a><span data-ttu-id="d2c78-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d2c78-106">Input</span></span>

### <a name="rng--range"></a><span data-ttu-id="d2c78-107">RNG: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="d2c78-107">rng : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="d2c78-108">Libovolný rozsah</span><span class="sxs-lookup"><span data-stu-id="d2c78-108">Any range</span></span>



## <a name="output--bool"></a><span data-ttu-id="d2c78-109">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d2c78-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d2c78-110">True, pokud je a jenom pokud `rng` je prázdný</span><span class="sxs-lookup"><span data-stu-id="d2c78-110">True, if and only if `rng` is empty</span></span>