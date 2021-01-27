---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: ddaace8df6e4c47c4affe2eeffb8d8ce31f37327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845233"
---
# <a name="xbits-function"></a><span data-ttu-id="635f3-102">XBits – funkce</span><span class="sxs-lookup"><span data-stu-id="635f3-102">XBits function</span></span>

<span data-ttu-id="635f3-103">Obor názvů: [Microsoft.. bitové](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="635f3-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="635f3-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="635f3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="635f3-105">Vrací celé číslo představující X bitů pole operátorů Pauli.</span><span class="sxs-lookup"><span data-stu-id="635f3-105">Returns an integer representing the X bits of an array of Pauli operators.</span></span>

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="635f3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="635f3-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="635f3-107">Pauls: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="635f3-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="635f3-108">Pole operátorů Pauli, které se mají znázornit jako celé číslo.</span><span class="sxs-lookup"><span data-stu-id="635f3-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="635f3-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="635f3-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="635f3-110">Celé číslo $x $ s binární reprezentací $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, kde $p _i = $0, pokud je `paulis[i]` `PauliI` nebo `PauliZ` a kde $p _i = $1, pokud `paulis[i]` je `PauliX` nebo `PauliY` .</span><span class="sxs-lookup"><span data-stu-id="635f3-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliZ` and where $p_i = 1$ if `paulis[i]` is `PauliX` or `PauliY`.</span></span>

## <a name="remarks"></a><span data-ttu-id="635f3-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="635f3-111">Remarks</span></span>

<span data-ttu-id="635f3-112">Funkce bude vyvolána, pokud `paulis` je délka pole větší než 63.</span><span class="sxs-lookup"><span data-stu-id="635f3-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="635f3-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="635f3-113">See Also</span></span>

- [<span data-ttu-id="635f3-114">Microsoft... bitový. ZBits</span><span class="sxs-lookup"><span data-stu-id="635f3-114">Microsoft.Quantum.Bitwise.ZBits</span></span>](xref:Microsoft.Quantum.Bitwise.ZBits)