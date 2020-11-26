---
uid: Microsoft.Quantum.Canon.CZ
title: CZ operace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 419082dbf8f96a9fe2dfabeab77e1823cb59a8f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207203"
---
# <a name="cz-operation"></a><span data-ttu-id="d41b2-102">CZ operace</span><span class="sxs-lookup"><span data-stu-id="d41b2-102">CZ operation</span></span>

<span data-ttu-id="d41b2-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d41b2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d41b2-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d41b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d41b2-105">Aplikuje bránu řízená – Z (CZ) na pár qubits.</span><span class="sxs-lookup"><span data-stu-id="d41b2-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="d41b2-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $, kde jsou řádky a sloupce uspořádány jako v průvodci koncepcemi.</span><span class="sxs-lookup"><span data-stu-id="d41b2-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d41b2-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="d41b2-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="d41b2-108">ovládací prvek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d41b2-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d41b2-109">Qubit ovládacího prvku pro hradlo CZ.</span><span class="sxs-lookup"><span data-stu-id="d41b2-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d41b2-110">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d41b2-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d41b2-111">Cílová qubit pro hradlo CZ</span><span class="sxs-lookup"><span data-stu-id="d41b2-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d41b2-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d41b2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d41b2-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d41b2-113">Remarks</span></span>

<span data-ttu-id="d41b2-114">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="d41b2-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```