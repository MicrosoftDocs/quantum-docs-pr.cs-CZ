---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Operace AllowAtMostNQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 3aa80767ac0f752e7be0efa2966c580ca3cb8f19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830917"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="0408e-102">Operace AllowAtMostNQubits</span><span class="sxs-lookup"><span data-stu-id="0408e-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="0408e-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0408e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0408e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0408e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0408e-105">Mezi voláním této operace a jejím sousedním objektem, výrazy, které mají maximálně daný počet dalších qubits, jsou přiděleny pomocí příkazů using.</span><span class="sxs-lookup"><span data-stu-id="0408e-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="0408e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="0408e-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="0408e-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0408e-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0408e-108">Maximální počet qubits, které mohou být přiděleny.</span><span class="sxs-lookup"><span data-stu-id="0408e-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="0408e-109">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="0408e-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="0408e-110">Zpráva, která se má zobrazit při selhání</span><span class="sxs-lookup"><span data-stu-id="0408e-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0408e-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0408e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="0408e-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="0408e-112">Example</span></span>

<span data-ttu-id="0408e-113">Následující fragment kódu se při spuštění na počítačích, které podporují tuto diagnostiku, nezdaří:</span><span class="sxs-lookup"><span data-stu-id="0408e-113">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
within {
    AllowAtMostNQubits(3, "Too many qubits allocated.");
} apply {
    // Fails since this allocates four qubits.
    using (register = Qubit[4]) {
    }
}
```

## <a name="remarks"></a><span data-ttu-id="0408e-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="0408e-114">Remarks</span></span>

<span data-ttu-id="0408e-115">Tato operace může být nahrazena operací no-op u cílů, které ji nepodporují.</span><span class="sxs-lookup"><span data-stu-id="0408e-115">This operation may be replaced by a no-op on targets which do not support it.</span></span>