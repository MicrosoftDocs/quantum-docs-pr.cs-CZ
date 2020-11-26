---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Operace CCNOT
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: 715796ddd915d80036933e3f1ceefa97aa62cecf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212473"
---
# <a name="ccnot-operation"></a><span data-ttu-id="f7040-102">Operace CCNOT</span><span class="sxs-lookup"><span data-stu-id="f7040-102">CCNOT operation</span></span>

<span data-ttu-id="f7040-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="f7040-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="f7040-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f7040-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f7040-105">Aplikuje bránu dvakrát ovládané – ne (CCNOT) na tři qubits.</span><span class="sxs-lookup"><span data-stu-id="f7040-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f7040-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f7040-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="f7040-107">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f7040-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f7040-108">První ovládací prvek qubit pro bránu CCNOT.</span><span class="sxs-lookup"><span data-stu-id="f7040-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="f7040-109">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f7040-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f7040-110">Druhý ovládací prvek qubit pro bránu CCNOT.</span><span class="sxs-lookup"><span data-stu-id="f7040-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f7040-111">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f7040-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f7040-112">Cílová qubit pro bránu CCNOT</span><span class="sxs-lookup"><span data-stu-id="f7040-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7040-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7040-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f7040-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f7040-114">Remarks</span></span>

<span data-ttu-id="f7040-115">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="f7040-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```