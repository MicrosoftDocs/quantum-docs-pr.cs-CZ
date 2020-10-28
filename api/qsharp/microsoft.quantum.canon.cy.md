---
uid: Microsoft.Quantum.Canon.CY
title: Operace CY
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 291891457ff39cf7092d17aa1d900dd0d35d9cf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704280"
---
# <a name="cy-operation"></a><span data-ttu-id="c8752-102">Operace CY</span><span class="sxs-lookup"><span data-stu-id="c8752-102">CY operation</span></span>

<span data-ttu-id="c8752-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c8752-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c8752-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c8752-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c8752-105">Aplikuje bránu řízená na Y (CY) na pár qubits.</span><span class="sxs-lookup"><span data-stu-id="c8752-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="c8752-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-i \\ \\ 0 & 0 & i & 0 \end{align}, $ $, kde jsou řádky a sloupce uspořádány jako v průvodci koncepty.</span><span class="sxs-lookup"><span data-stu-id="c8752-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="c8752-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="c8752-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="c8752-108">ovládací prvek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c8752-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c8752-109">Qubit ovládacího prvku pro bránu CY.</span><span class="sxs-lookup"><span data-stu-id="c8752-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c8752-110">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c8752-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c8752-111">Cílová qubit pro bránu CY</span><span class="sxs-lookup"><span data-stu-id="c8752-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c8752-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c8752-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c8752-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c8752-113">Remarks</span></span>

<span data-ttu-id="c8752-114">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="c8752-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```