---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Operace AllowAtMostNQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698176"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="e725f-102">Operace AllowAtMostNQubits</span><span class="sxs-lookup"><span data-stu-id="e725f-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="e725f-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e725f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e725f-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e725f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e725f-105">Mezi voláním této operace a jejím sousedním objektem, výrazy, které mají maximálně daný počet dalších qubits, jsou přiděleny pomocí příkazů using.</span><span class="sxs-lookup"><span data-stu-id="e725f-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="e725f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e725f-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="e725f-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e725f-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e725f-108">Maximální počet qubits, které mohou být přiděleny.</span><span class="sxs-lookup"><span data-stu-id="e725f-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="e725f-109">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e725f-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e725f-110">Zpráva, která se má zobrazit při selhání</span><span class="sxs-lookup"><span data-stu-id="e725f-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e725f-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e725f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e725f-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e725f-112">Remarks</span></span>

<span data-ttu-id="e725f-113">Tato operace může být nahrazena operací no-op u cílů, které ji nepodporují.</span><span class="sxs-lookup"><span data-stu-id="e725f-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>