---
uid: Microsoft.Quantum.Canon.CX
title: Operace CX
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: e27b30a6b4609daaac2cc5eda68120115777af0c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840757"
---
# <a name="cx-operation"></a><span data-ttu-id="aa8e1-102">Operace CX</span><span class="sxs-lookup"><span data-stu-id="aa8e1-102">CX operation</span></span>

<span data-ttu-id="aa8e1-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa8e1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa8e1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa8e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa8e1-105">Aplikuje bránu řízená – X (CX) na pár qubits.</span><span class="sxs-lookup"><span data-stu-id="aa8e1-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="aa8e1-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $, kde jsou řádky a sloupce uspořádány jako v průvodci koncepty.</span><span class="sxs-lookup"><span data-stu-id="aa8e1-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="aa8e1-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="aa8e1-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="aa8e1-108">ovládací prvek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aa8e1-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aa8e1-109">Qubit ovládacího prvku pro bránu CX.</span><span class="sxs-lookup"><span data-stu-id="aa8e1-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="aa8e1-110">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aa8e1-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aa8e1-111">Cílová qubit pro bránu CX.</span><span class="sxs-lookup"><span data-stu-id="aa8e1-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa8e1-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa8e1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="aa8e1-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="aa8e1-113">Remarks</span></span>

<span data-ttu-id="aa8e1-114">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="aa8e1-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="aa8e1-115">a na:</span><span class="sxs-lookup"><span data-stu-id="aa8e1-115">and to:</span></span>

```qsharp
CNOT(control, target);
```