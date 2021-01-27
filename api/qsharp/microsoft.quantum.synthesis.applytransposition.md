---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Operace ApplyTransposition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 46cf8c2c891aa02b0d8a1397e6c2b7a4b8618048
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855568"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="8ef08-102">Operace ApplyTransposition</span><span class="sxs-lookup"><span data-stu-id="8ef08-102">ApplyTransposition operation</span></span>

<span data-ttu-id="8ef08-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="8ef08-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="8ef08-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ef08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="8ef08-105">Popis</span><span class="sxs-lookup"><span data-stu-id="8ef08-105">Description</span></span>

<span data-ttu-id="8ef08-106">Tato operace zamění amplitudu s indexem `a` s amplitudou v indexu `b` v daném stavu – vektor `register` délky $n $.</span><span class="sxs-lookup"><span data-stu-id="8ef08-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="8ef08-107">Pokud `a` je rovno `b` , nemění se stavový vektor.</span><span class="sxs-lookup"><span data-stu-id="8ef08-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="8ef08-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="8ef08-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="8ef08-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8ef08-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8ef08-110">První index (musí být hodnota od 0 do $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="8ef08-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="8ef08-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8ef08-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8ef08-112">Druhý index (musí být hodnota od 0 do $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="8ef08-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="8ef08-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8ef08-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8ef08-114">Seznam $n $ qubits, na který se aplikuje provedení.</span><span class="sxs-lookup"><span data-stu-id="8ef08-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ef08-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ef08-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="8ef08-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="8ef08-116">Example</span></span>

<span data-ttu-id="8ef08-117">Připravte jednotnou pozici číselných stavů $ | 1 \ rangle $, $ | 2 \ rangle $ a $ | 3 \ rangle $ on 2 qubits.</span><span class="sxs-lookup"><span data-stu-id="8ef08-117">Prepare a uniform superposition of number states $|1\rangle$, $|2\rangle$, and $|3\rangle$ on 2 qubits.</span></span>

```qsharp
using (qubits = Qubit[2]) {
  let register = LittleEndian(qubits);
  PrepareUniformSuperposition(3, register);
  ApplyTransposition(0, 3, register);
}
```