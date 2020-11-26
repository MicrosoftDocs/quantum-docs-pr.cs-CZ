---
uid: Microsoft.Quantum.Canon.CY
title: Operace CY
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 4a1a533421dd9205e973d5e8237d67b20bc4886d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216570"
---
# <a name="cy-operation"></a><span data-ttu-id="a65d1-102">Operace CY</span><span class="sxs-lookup"><span data-stu-id="a65d1-102">CY operation</span></span>

<span data-ttu-id="a65d1-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a65d1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a65d1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a65d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a65d1-105">Aplikuje bránu řízená na Y (CY) na pár qubits.</span><span class="sxs-lookup"><span data-stu-id="a65d1-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="a65d1-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-i \\ \\ 0 & 0 & i & 0 \end{align}, $ $, kde jsou řádky a sloupce uspořádány jako v průvodci koncepty.</span><span class="sxs-lookup"><span data-stu-id="a65d1-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a65d1-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="a65d1-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="a65d1-108">ovládací prvek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a65d1-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a65d1-109">Qubit ovládacího prvku pro bránu CY.</span><span class="sxs-lookup"><span data-stu-id="a65d1-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a65d1-110">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a65d1-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a65d1-111">Cílová qubit pro bránu CY</span><span class="sxs-lookup"><span data-stu-id="a65d1-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a65d1-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a65d1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a65d1-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a65d1-113">Remarks</span></span>

<span data-ttu-id="a65d1-114">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="a65d1-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```