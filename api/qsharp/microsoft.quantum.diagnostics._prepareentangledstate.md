---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: operace _prepareEntangledState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 97a55b4bb85095c7d8e8432dfcd1c6d6f7e93cdc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223931"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="24658-102">operace _prepareEntangledState</span><span class="sxs-lookup"><span data-stu-id="24658-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="24658-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="24658-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="24658-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="24658-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="24658-105">Vzhledem k dvěma registrům připraví maximální entangled stav mezi každou dvojici qubits na příslušných registrech.</span><span class="sxs-lookup"><span data-stu-id="24658-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="24658-106">Všechny qubits musí začínat ve stavu | 0 ⟩.</span><span class="sxs-lookup"><span data-stu-id="24658-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="24658-107">Výsledkem je, že odpovídající páry qubits z každého registru jsou v $ \bra{\ beta_ {00} } \ket{\ Beta_ {00} } $.</span><span class="sxs-lookup"><span data-stu-id="24658-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="24658-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="24658-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="24658-109">Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="24658-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="24658-110">Pole qubit ve stavu $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="24658-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="24658-111">Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="24658-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="24658-112">Pole qubit ve stavu $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="24658-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="24658-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24658-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

