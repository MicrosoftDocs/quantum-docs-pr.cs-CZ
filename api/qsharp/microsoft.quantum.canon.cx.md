---
uid: Microsoft.Quantum.Canon.CX
title: Operace CX
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 4eaecf372f3054de4886b1e42c6b4ce386a22f73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207237"
---
# <a name="cx-operation"></a><span data-ttu-id="9957d-102">Operace CX</span><span class="sxs-lookup"><span data-stu-id="9957d-102">CX operation</span></span>

<span data-ttu-id="9957d-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9957d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9957d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9957d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9957d-105">Aplikuje bránu řízená – X (CX) na pár qubits.</span><span class="sxs-lookup"><span data-stu-id="9957d-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="9957d-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $, kde jsou řádky a sloupce uspořádány jako v průvodci koncepty.</span><span class="sxs-lookup"><span data-stu-id="9957d-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9957d-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="9957d-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="9957d-108">ovládací prvek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9957d-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9957d-109">Qubit ovládacího prvku pro bránu CX.</span><span class="sxs-lookup"><span data-stu-id="9957d-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9957d-110">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9957d-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9957d-111">Cílová qubit pro bránu CX.</span><span class="sxs-lookup"><span data-stu-id="9957d-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9957d-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9957d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9957d-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="9957d-113">Remarks</span></span>

<span data-ttu-id="9957d-114">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="9957d-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="9957d-115">a na:</span><span class="sxs-lookup"><span data-stu-id="9957d-115">and to:</span></span>

```qsharp
CNOT(control, target);
```