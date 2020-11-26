---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Operace ApplyTransposition
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203310"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="d5d54-102">Operace ApplyTransposition</span><span class="sxs-lookup"><span data-stu-id="d5d54-102">ApplyTransposition operation</span></span>

<span data-ttu-id="d5d54-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d5d54-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d5d54-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d5d54-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d5d54-105">Popis</span><span class="sxs-lookup"><span data-stu-id="d5d54-105">Description</span></span>

<span data-ttu-id="d5d54-106">Tato operace zamění amplitudu s indexem `a` s amplitudou v indexu `b` v daném stavu – vektor `register` délky $n $.</span><span class="sxs-lookup"><span data-stu-id="d5d54-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="d5d54-107">Pokud `a` je rovno `b` , nemění se stavový vektor.</span><span class="sxs-lookup"><span data-stu-id="d5d54-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="d5d54-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="d5d54-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="d5d54-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d5d54-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d5d54-110">První index (musí být hodnota od 0 do $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="d5d54-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="d5d54-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d5d54-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d5d54-112">Druhý index (musí být hodnota od 0 do $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="d5d54-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="d5d54-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d5d54-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d5d54-114">Seznam $n $ qubits, na který se aplikuje provedení.</span><span class="sxs-lookup"><span data-stu-id="d5d54-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5d54-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5d54-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

