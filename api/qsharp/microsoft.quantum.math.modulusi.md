---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 7bad044db9e2229c85cb3909dc4802bceaee6382
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847291"
---
# <a name="modulusi-function"></a><span data-ttu-id="d90a6-102">ModulusI – funkce</span><span class="sxs-lookup"><span data-stu-id="d90a6-102">ModulusI function</span></span>

<span data-ttu-id="d90a6-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d90a6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d90a6-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d90a6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d90a6-105">Vypočítá kanonický zbytek `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="d90a6-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="d90a6-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d90a6-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="d90a6-107">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d90a6-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d90a6-108">Hodnota, kterou je vypočítáno reziduum</span><span class="sxs-lookup"><span data-stu-id="d90a6-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="d90a6-109">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d90a6-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d90a6-110">Zbytky, podle kterých jsou zbytky vzaty, musí být kladné</span><span class="sxs-lookup"><span data-stu-id="d90a6-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="d90a6-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d90a6-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d90a6-112">Celé číslo $r $ mezi 0 a `modulus - 1` to `value - r` je dělitelé modulem.</span><span class="sxs-lookup"><span data-stu-id="d90a6-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="d90a6-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d90a6-113">Remarks</span></span>

<span data-ttu-id="d90a6-114">Tato funkce se chová jinak, než se operátor `%` chová v jazyce C# a Q #, protože ve výsledku je vždy nezáporné celé číslo mezi 0 a `modulus - 1` , i když je hodnota záporná.</span><span class="sxs-lookup"><span data-stu-id="d90a6-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>