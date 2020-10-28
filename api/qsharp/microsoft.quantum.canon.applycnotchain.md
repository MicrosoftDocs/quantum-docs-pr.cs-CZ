---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: Operace ApplyCNOTChain
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: c98fe24ca352952162acb7a9c4fc93d5da4285b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705448"
---
# <a name="applycnotchain-operation"></a><span data-ttu-id="ce27b-102">Operace ApplyCNOTChain</span><span class="sxs-lookup"><span data-stu-id="ce27b-102">ApplyCNOTChain operation</span></span>

<span data-ttu-id="ce27b-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ce27b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ce27b-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ce27b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ce27b-105">Vypočítá paritu registru qubits na místě.</span><span class="sxs-lookup"><span data-stu-id="ce27b-105">Computes the parity of a register of qubits in-place.</span></span>

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ce27b-106">Popis</span><span class="sxs-lookup"><span data-stu-id="ce27b-106">Description</span></span>

<span data-ttu-id="ce27b-107">Tato operace transformuje stav svého vstupu jako $ $ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_ {n-1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_ {n-1}}.</span><span class="sxs-lookup"><span data-stu-id="ce27b-107">This operation transforms the state of its input as $$ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_{n - 1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_{n - 1}}.</span></span>
<span data-ttu-id="ce27b-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="ce27b-108">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="ce27b-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="ce27b-109">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="ce27b-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ce27b-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ce27b-111">Pole qubits, jehož parita má být vypočítána a uložena.</span><span class="sxs-lookup"><span data-stu-id="ce27b-111">Array of qubits whose parity is to be computed and stored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ce27b-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce27b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

