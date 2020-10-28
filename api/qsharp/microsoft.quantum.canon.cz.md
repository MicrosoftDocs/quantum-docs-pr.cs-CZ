---
uid: Microsoft.Quantum.Canon.CZ
title: CZ operace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: bc38cd43a0dcaf7aea735ef6468a394e91c85593
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704272"
---
# <a name="cz-operation"></a><span data-ttu-id="fd100-102">CZ operace</span><span class="sxs-lookup"><span data-stu-id="fd100-102">CZ operation</span></span>

<span data-ttu-id="fd100-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fd100-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fd100-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fd100-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fd100-105">Aplikuje bránu řízená – Z (CZ) na pár qubits.</span><span class="sxs-lookup"><span data-stu-id="fd100-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="fd100-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $, kde jsou řádky a sloupce uspořádány jako v průvodci koncepcemi.</span><span class="sxs-lookup"><span data-stu-id="fd100-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="fd100-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="fd100-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="fd100-108">ovládací prvek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fd100-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fd100-109">Qubit ovládacího prvku pro hradlo CZ.</span><span class="sxs-lookup"><span data-stu-id="fd100-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="fd100-110">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fd100-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fd100-111">Cílová qubit pro hradlo CZ</span><span class="sxs-lookup"><span data-stu-id="fd100-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fd100-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fd100-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fd100-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fd100-113">Remarks</span></span>

<span data-ttu-id="fd100-114">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="fd100-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```