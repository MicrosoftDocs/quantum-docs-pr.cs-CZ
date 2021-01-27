---
uid: Microsoft.Quantum.Canon.CZ
title: CZ operace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: cef1544fb76d561cfd0949c84c487550d523bb85
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840705"
---
# <a name="cz-operation"></a><span data-ttu-id="c1e13-102">CZ operace</span><span class="sxs-lookup"><span data-stu-id="c1e13-102">CZ operation</span></span>

<span data-ttu-id="c1e13-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c1e13-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c1e13-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c1e13-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c1e13-105">Aplikuje bránu řízená – Z (CZ) na pár qubits.</span><span class="sxs-lookup"><span data-stu-id="c1e13-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="c1e13-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $, kde jsou řádky a sloupce uspořádány jako v průvodci koncepcemi.</span><span class="sxs-lookup"><span data-stu-id="c1e13-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c1e13-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="c1e13-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="c1e13-108">ovládací prvek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c1e13-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c1e13-109">Qubit ovládacího prvku pro hradlo CZ.</span><span class="sxs-lookup"><span data-stu-id="c1e13-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c1e13-110">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c1e13-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c1e13-111">Cílová qubit pro hradlo CZ</span><span class="sxs-lookup"><span data-stu-id="c1e13-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c1e13-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1e13-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c1e13-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c1e13-113">Remarks</span></span>

<span data-ttu-id="c1e13-114">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="c1e13-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```