---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 3f698a00b2c8d94b7cb3cca4f1721c659918f4a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708260"
---
# <a name="modulusi-function"></a><span data-ttu-id="59138-102">ModulusI – funkce</span><span class="sxs-lookup"><span data-stu-id="59138-102">ModulusI function</span></span>

<span data-ttu-id="59138-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="59138-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="59138-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="59138-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="59138-105">Vypočítá kanonický zbytek `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="59138-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="59138-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="59138-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="59138-107">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59138-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="59138-108">Hodnota, kterou je vypočítáno reziduum</span><span class="sxs-lookup"><span data-stu-id="59138-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="59138-109">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59138-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="59138-110">Zbytky, podle kterých jsou zbytky vzaty, musí být kladné</span><span class="sxs-lookup"><span data-stu-id="59138-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="59138-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59138-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="59138-112">Celé číslo $r $ mezi 0 a `modulus - 1` to `value - r` je dělitelé modulem.</span><span class="sxs-lookup"><span data-stu-id="59138-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="59138-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="59138-113">Remarks</span></span>

<span data-ttu-id="59138-114">Tato funkce se chová jinak, než se operátor `%` chová v jazyce C# a Q #, protože ve výsledku je vždy kladné celé číslo mezi 0 a `modulus - 1` , i když je hodnota záporná.</span><span class="sxs-lookup"><span data-stu-id="59138-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>