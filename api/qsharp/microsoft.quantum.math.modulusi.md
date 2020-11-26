---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6bbb3877b93e1fc6b38f85a716ba617311c7cfba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227773"
---
# <a name="modulusi-function"></a><span data-ttu-id="55a40-102">ModulusI – funkce</span><span class="sxs-lookup"><span data-stu-id="55a40-102">ModulusI function</span></span>

<span data-ttu-id="55a40-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="55a40-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="55a40-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55a40-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55a40-105">Vypočítá kanonický zbytek `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="55a40-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="55a40-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="55a40-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="55a40-107">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55a40-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55a40-108">Hodnota, kterou je vypočítáno reziduum</span><span class="sxs-lookup"><span data-stu-id="55a40-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="55a40-109">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55a40-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55a40-110">Zbytky, podle kterých jsou zbytky vzaty, musí být kladné</span><span class="sxs-lookup"><span data-stu-id="55a40-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="55a40-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55a40-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55a40-112">Celé číslo $r $ mezi 0 a `modulus - 1` to `value - r` je dělitelé modulem.</span><span class="sxs-lookup"><span data-stu-id="55a40-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="55a40-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="55a40-113">Remarks</span></span>

<span data-ttu-id="55a40-114">Tato funkce se chová jinak, než se operátor `%` chová v jazyce C# a Q #, protože ve výsledku je vždy kladné celé číslo mezi 0 a `modulus - 1` , i když je hodnota záporná.</span><span class="sxs-lookup"><span data-stu-id="55a40-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>