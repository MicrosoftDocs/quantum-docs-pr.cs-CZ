---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: f66b8ef0370e898dd1d095ff2840c91566f32cb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705552"
---
# <a name="zbits-function"></a><span data-ttu-id="57a14-102">ZBits – funkce</span><span class="sxs-lookup"><span data-stu-id="57a14-102">ZBits function</span></span>

<span data-ttu-id="57a14-103">Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="57a14-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="57a14-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="57a14-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="57a14-105">Vrací celé číslo představující bity Z pole operátorů Pauli.</span><span class="sxs-lookup"><span data-stu-id="57a14-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="57a14-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="57a14-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="57a14-107">Pauls: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="57a14-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="57a14-108">Pole operátorů Pauli, které se mají znázornit jako celé číslo.</span><span class="sxs-lookup"><span data-stu-id="57a14-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="57a14-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57a14-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="57a14-110">Celé číslo $x $ s binární reprezentací $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, kde $p _i = $0, pokud je `paulis[i]` `PauliI` nebo `PauliX` a kde $p _i = $1, pokud `paulis[i]` je `PauliY` nebo `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="57a14-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="57a14-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="57a14-111">Remarks</span></span>

<span data-ttu-id="57a14-112">Funkce bude vyvolána, pokud `paulis` je délka pole větší než 63.</span><span class="sxs-lookup"><span data-stu-id="57a14-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="57a14-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="57a14-113">See Also</span></span>

- [<span data-ttu-id="57a14-114">Microsoft... bitový. XBits</span><span class="sxs-lookup"><span data-stu-id="57a14-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)