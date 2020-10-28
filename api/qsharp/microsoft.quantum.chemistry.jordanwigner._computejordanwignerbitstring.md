---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 31b957a435c3f578bc03d432609cde14c2ef5ced
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698645"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="53584-102">_ComputeJordanWignerBitString funkce</span><span class="sxs-lookup"><span data-stu-id="53584-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="53584-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="53584-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="53584-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53584-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53584-105">Vypočítá komponentu Z Jordánska – Wigner řetězec mezi fermion indexy v operátoru fermionic s sudým počtem operátorů pro vytváření a Annihilation.</span><span class="sxs-lookup"><span data-stu-id="53584-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="53584-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="53584-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="53584-107">nFermions: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53584-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53584-108">Počet fermions v systému.</span><span class="sxs-lookup"><span data-stu-id="53584-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="53584-109">idxFermions: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="53584-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="53584-110">indexy operátorů fermionic</span><span class="sxs-lookup"><span data-stu-id="53584-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="53584-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="53584-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="53584-112">BITSTRING `Bool[]` , `true` kde má `PauliZ` být použita.</span><span class="sxs-lookup"><span data-stu-id="53584-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>