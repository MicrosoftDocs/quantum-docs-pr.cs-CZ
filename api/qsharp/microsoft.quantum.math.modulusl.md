---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: e7e692059051fde295634c37892ec54e2cf1b095
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709123"
---
# <a name="modulusl-function"></a><span data-ttu-id="a2c63-102">ModulusL – funkce</span><span class="sxs-lookup"><span data-stu-id="a2c63-102">ModulusL function</span></span>

<span data-ttu-id="a2c63-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a2c63-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a2c63-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a2c63-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a2c63-105">Vypočítá kanonický zbytek `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="a2c63-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="a2c63-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a2c63-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="a2c63-107">hodnota: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a2c63-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a2c63-108">Hodnota, kterou je vypočítáno reziduum</span><span class="sxs-lookup"><span data-stu-id="a2c63-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="a2c63-109">Modulus: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a2c63-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a2c63-110">Zbytky, podle kterých jsou zbytky vzaty, musí být kladné</span><span class="sxs-lookup"><span data-stu-id="a2c63-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="a2c63-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a2c63-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a2c63-112">Celé číslo $r $ mezi 0 a `modulus - 1` to `value - r` je dělitelé modulem.</span><span class="sxs-lookup"><span data-stu-id="a2c63-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="a2c63-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a2c63-113">Remarks</span></span>

<span data-ttu-id="a2c63-114">Tato funkce se chová jinak, než se operátor `%` chová v jazyce C# a Q #, protože ve výsledku je vždy kladné celé číslo mezi 0 a `modulus - 1` , i když je hodnota záporná.</span><span class="sxs-lookup"><span data-stu-id="a2c63-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>