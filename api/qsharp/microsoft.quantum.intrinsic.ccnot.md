---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Operace CCNOT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697741"
---
# <a name="ccnot-operation"></a><span data-ttu-id="e991a-102">Operace CCNOT</span><span class="sxs-lookup"><span data-stu-id="e991a-102">CCNOT operation</span></span>

<span data-ttu-id="e991a-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="e991a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="e991a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e991a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e991a-105">Aplikuje bránu dvakrát ovládané – ne (CCNOT) na tři qubits.</span><span class="sxs-lookup"><span data-stu-id="e991a-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e991a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e991a-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="e991a-107">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e991a-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e991a-108">První ovládací prvek qubit pro bránu CCNOT.</span><span class="sxs-lookup"><span data-stu-id="e991a-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="e991a-109">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e991a-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e991a-110">Druhý ovládací prvek qubit pro bránu CCNOT.</span><span class="sxs-lookup"><span data-stu-id="e991a-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e991a-111">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e991a-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e991a-112">Cílová qubit pro bránu CCNOT</span><span class="sxs-lookup"><span data-stu-id="e991a-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e991a-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e991a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e991a-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e991a-114">Remarks</span></span>

<span data-ttu-id="e991a-115">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="e991a-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```