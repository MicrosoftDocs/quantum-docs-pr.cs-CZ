---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: Operace CNOT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 2fb5b4df189fb3ab23b2ca5cb273b2451ffcc067
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708080"
---
# <a name="cnot-operation"></a><span data-ttu-id="a2b8c-102">Operace CNOT</span><span class="sxs-lookup"><span data-stu-id="a2b8c-102">CNOT operation</span></span>

<span data-ttu-id="a2b8c-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a2b8c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a2b8c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a2b8c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a2b8c-105">Aplikuje bránu řízeného NOT (CNOT) na pár qubits.</span><span class="sxs-lookup"><span data-stu-id="a2b8c-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="a2b8c-106">\begin{align} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span><span class="sxs-lookup"><span data-stu-id="a2b8c-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="a2b8c-107">místo, kde jsou řádky a sloupce seřazené jako v průvodci koncepcemi.</span><span class="sxs-lookup"><span data-stu-id="a2b8c-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="a2b8c-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="a2b8c-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="a2b8c-109">ovládací prvek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a2b8c-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a2b8c-110">Qubit ovládacího prvku pro bránu CNOT.</span><span class="sxs-lookup"><span data-stu-id="a2b8c-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a2b8c-111">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a2b8c-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a2b8c-112">Cílová qubit pro bránu CNOT</span><span class="sxs-lookup"><span data-stu-id="a2b8c-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a2b8c-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2b8c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a2b8c-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a2b8c-114">Remarks</span></span>

<span data-ttu-id="a2b8c-115">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="a2b8c-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```