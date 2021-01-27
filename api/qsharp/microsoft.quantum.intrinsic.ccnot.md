---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Operace CCNOT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: a9186269a868c2ac9d2f15727a3b0ed1bfec3fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819033"
---
# <a name="ccnot-operation"></a><span data-ttu-id="75e30-102">Operace CCNOT</span><span class="sxs-lookup"><span data-stu-id="75e30-102">CCNOT operation</span></span>

<span data-ttu-id="75e30-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="75e30-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="75e30-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="75e30-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="75e30-105">Aplikuje bránu dvakrát ovládané – ne (CCNOT) na tři qubits.</span><span class="sxs-lookup"><span data-stu-id="75e30-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="75e30-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="75e30-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="75e30-107">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="75e30-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="75e30-108">První ovládací prvek qubit pro bránu CCNOT.</span><span class="sxs-lookup"><span data-stu-id="75e30-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="75e30-109">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="75e30-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="75e30-110">Druhý ovládací prvek qubit pro bránu CCNOT.</span><span class="sxs-lookup"><span data-stu-id="75e30-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="75e30-111">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="75e30-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="75e30-112">Cílová qubit pro bránu CCNOT</span><span class="sxs-lookup"><span data-stu-id="75e30-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="75e30-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="75e30-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="75e30-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="75e30-114">Remarks</span></span>

<span data-ttu-id="75e30-115">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="75e30-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```