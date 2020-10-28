---
uid: Microsoft.Quantum.Canon.CX
title: Operace CX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: c430525b71ad4ef0812d90a8ff20c41a5d5b8708
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704288"
---
# <a name="cx-operation"></a><span data-ttu-id="869fe-102">Operace CX</span><span class="sxs-lookup"><span data-stu-id="869fe-102">CX operation</span></span>

<span data-ttu-id="869fe-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="869fe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="869fe-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="869fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="869fe-105">Aplikuje bránu řízená – X (CX) na pár qubits.</span><span class="sxs-lookup"><span data-stu-id="869fe-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="869fe-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $, kde jsou řádky a sloupce uspořádány jako v průvodci koncepty.</span><span class="sxs-lookup"><span data-stu-id="869fe-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="869fe-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="869fe-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="869fe-108">ovládací prvek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="869fe-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="869fe-109">Qubit ovládacího prvku pro bránu CX.</span><span class="sxs-lookup"><span data-stu-id="869fe-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="869fe-110">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="869fe-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="869fe-111">Cílová qubit pro bránu CX.</span><span class="sxs-lookup"><span data-stu-id="869fe-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="869fe-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="869fe-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="869fe-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="869fe-113">Remarks</span></span>

<span data-ttu-id="869fe-114">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="869fe-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="869fe-115">a na:</span><span class="sxs-lookup"><span data-stu-id="869fe-115">and to:</span></span>

```qsharp
CNOT(control, target);
```