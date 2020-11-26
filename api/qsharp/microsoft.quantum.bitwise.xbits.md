---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 969be01204bad497496ff24cb64213f5fe1f089b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209753"
---
# <a name="xbits-function"></a><span data-ttu-id="fb02b-102">XBits – funkce</span><span class="sxs-lookup"><span data-stu-id="fb02b-102">XBits function</span></span>

<span data-ttu-id="fb02b-103">Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="fb02b-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="fb02b-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fb02b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fb02b-105">Vrací celé číslo představující X bitů pole operátorů Pauli.</span><span class="sxs-lookup"><span data-stu-id="fb02b-105">Returns an integer representing the X bits of an array of Pauli operators.</span></span>

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="fb02b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fb02b-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="fb02b-107">Pauls: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="fb02b-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="fb02b-108">Pole operátorů Pauli, které se mají znázornit jako celé číslo.</span><span class="sxs-lookup"><span data-stu-id="fb02b-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="fb02b-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fb02b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fb02b-110">Celé číslo $x $ s binární reprezentací $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, kde $p _i = $0, pokud je `paulis[i]` `PauliI` nebo `PauliZ` a kde $p _i = $1, pokud `paulis[i]` je `PauliX` nebo `PauliY` .</span><span class="sxs-lookup"><span data-stu-id="fb02b-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliZ` and where $p_i = 1$ if `paulis[i]` is `PauliX` or `PauliY`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fb02b-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fb02b-111">Remarks</span></span>

<span data-ttu-id="fb02b-112">Funkce bude vyvolána, pokud `paulis` je délka pole větší než 63.</span><span class="sxs-lookup"><span data-stu-id="fb02b-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb02b-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="fb02b-113">See Also</span></span>

- [<span data-ttu-id="fb02b-114">Microsoft... bitový. ZBits</span><span class="sxs-lookup"><span data-stu-id="fb02b-114">Microsoft.Quantum.Bitwise.ZBits</span></span>](xref:Microsoft.Quantum.Bitwise.ZBits)