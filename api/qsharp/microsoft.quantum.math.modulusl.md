---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842749"
---
# <a name="modulusl-function"></a><span data-ttu-id="2fdb4-102">ModulusL – funkce</span><span class="sxs-lookup"><span data-stu-id="2fdb4-102">ModulusL function</span></span>

<span data-ttu-id="2fdb4-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2fdb4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2fdb4-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2fdb4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2fdb4-105">Vypočítá kanonický zbytek `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="2fdb4-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="2fdb4-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2fdb4-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="2fdb4-107">hodnota: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2fdb4-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2fdb4-108">Hodnota, kterou je vypočítáno reziduum</span><span class="sxs-lookup"><span data-stu-id="2fdb4-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="2fdb4-109">Modulus: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2fdb4-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2fdb4-110">Zbytky, podle kterých jsou zbytky vzaty, musí být kladné</span><span class="sxs-lookup"><span data-stu-id="2fdb4-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="2fdb4-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2fdb4-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2fdb4-112">Celé číslo $r $ mezi 0 a `modulus - 1` to `value - r` je dělitelé modulem.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="2fdb4-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2fdb4-113">Remarks</span></span>

<span data-ttu-id="2fdb4-114">Tato funkce se chová jinak, než se operátor `%` chová v jazyce C# a Q #, protože ve výsledku je vždy nezáporné celé číslo mezi 0 a `modulus - 1` , i když je hodnota záporná.</span><span class="sxs-lookup"><span data-stu-id="2fdb4-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>