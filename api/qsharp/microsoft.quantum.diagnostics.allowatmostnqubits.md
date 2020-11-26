---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Operace AllowAtMostNQubits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 5376b6f39d12d664342fbf71e67442c6ef8a0827
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202545"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="c9b0a-102">Operace AllowAtMostNQubits</span><span class="sxs-lookup"><span data-stu-id="c9b0a-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="c9b0a-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c9b0a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c9b0a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9b0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9b0a-105">Mezi voláním této operace a jejím sousedním objektem, výrazy, které mají maximálně daný počet dalších qubits, jsou přiděleny pomocí příkazů using.</span><span class="sxs-lookup"><span data-stu-id="c9b0a-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="c9b0a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c9b0a-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="c9b0a-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9b0a-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c9b0a-108">Maximální počet qubits, které mohou být přiděleny.</span><span class="sxs-lookup"><span data-stu-id="c9b0a-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="c9b0a-109">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c9b0a-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="c9b0a-110">Zpráva, která se má zobrazit při selhání</span><span class="sxs-lookup"><span data-stu-id="c9b0a-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c9b0a-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c9b0a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c9b0a-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c9b0a-112">Remarks</span></span>

<span data-ttu-id="c9b0a-113">Tato operace může být nahrazena operací no-op u cílů, které ji nepodporují.</span><span class="sxs-lookup"><span data-stu-id="c9b0a-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>