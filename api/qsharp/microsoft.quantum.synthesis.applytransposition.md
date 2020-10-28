---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Operace ApplyTransposition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709190"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="f7b46-102">Operace ApplyTransposition</span><span class="sxs-lookup"><span data-stu-id="f7b46-102">ApplyTransposition operation</span></span>

<span data-ttu-id="f7b46-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f7b46-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f7b46-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7b46-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="f7b46-105">Popis</span><span class="sxs-lookup"><span data-stu-id="f7b46-105">Description</span></span>

<span data-ttu-id="f7b46-106">Tato operace zamění amplitudu s indexem `a` s amplitudou v indexu `b` v daném stavu – vektor `register` délky $n $.</span><span class="sxs-lookup"><span data-stu-id="f7b46-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="f7b46-107">Pokud `a` je rovno `b` , nemění se stavový vektor.</span><span class="sxs-lookup"><span data-stu-id="f7b46-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="f7b46-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="f7b46-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="f7b46-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f7b46-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f7b46-110">První index (musí být hodnota od 0 do $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="f7b46-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="f7b46-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f7b46-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f7b46-112">Druhý index (musí být hodnota od 0 do $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="f7b46-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f7b46-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f7b46-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f7b46-114">Seznam $n $ qubits, na který se aplikuje provedení.</span><span class="sxs-lookup"><span data-stu-id="f7b46-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7b46-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7b46-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

