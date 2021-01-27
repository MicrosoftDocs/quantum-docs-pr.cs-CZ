---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: operace _prepareEntangledState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 5a74978a536a92dafae0b532805bd8e8ae1c888e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830975"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="ac647-102">operace _prepareEntangledState</span><span class="sxs-lookup"><span data-stu-id="ac647-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="ac647-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ac647-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ac647-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ac647-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ac647-105">Vzhledem k dvěma registrům připraví maximální entangled stav mezi každou dvojici qubits na příslušných registrech.</span><span class="sxs-lookup"><span data-stu-id="ac647-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="ac647-106">Všechny qubits musí začínat ve stavu | 0 ⟩.</span><span class="sxs-lookup"><span data-stu-id="ac647-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="ac647-107">Výsledkem je, že odpovídající páry qubits z každého registru jsou v $ \bra{\ beta_ {00} } \ket{\ Beta_ {00} } $.</span><span class="sxs-lookup"><span data-stu-id="ac647-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ac647-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="ac647-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="ac647-109">Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ac647-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ac647-110">Pole qubit ve stavu $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="ac647-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="ac647-111">Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ac647-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ac647-112">Pole qubit ve stavu $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="ac647-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="ac647-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac647-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

