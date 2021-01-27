---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Operace ApplyDeltaParity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: f5f1d74274994f042f1bc3f2e0d5332f504be02c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851100"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="b03d9-102">Operace ApplyDeltaParity</span><span class="sxs-lookup"><span data-stu-id="b03d9-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="b03d9-103">Obor názvů: [Microsoft. Prohledávejte. Research. chemie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b03d9-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="b03d9-104">Balíček: [Microsoft. prostudoval. Research. chemie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b03d9-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="b03d9-105">Počítá rozdíl v paritě mezi předchozím PQRS... výrazy a další PQRS... doby.</span><span class="sxs-lookup"><span data-stu-id="b03d9-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="b03d9-106">Tento rozdíl je vypočítán na základě pomocného qubitu.</span><span class="sxs-lookup"><span data-stu-id="b03d9-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b03d9-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="b03d9-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="b03d9-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b03d9-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b03d9-109">Seznam indexů pro předchozí PQRS... uvedenými.</span><span class="sxs-lookup"><span data-stu-id="b03d9-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="b03d9-110">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b03d9-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b03d9-111">Seznam indexů pro další PQRS... uvedenými.</span><span class="sxs-lookup"><span data-stu-id="b03d9-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="b03d9-112">AUX: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b03d9-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b03d9-113">Pomocné qubit, na které se ukládají výsledky výpočtů parity.</span><span class="sxs-lookup"><span data-stu-id="b03d9-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="b03d9-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b03d9-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b03d9-115">Qubit se jednalo o všechny PQRS... uvedenými.</span><span class="sxs-lookup"><span data-stu-id="b03d9-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b03d9-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b03d9-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b03d9-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b03d9-117">Remarks</span></span>

<span data-ttu-id="b03d9-118">Předpokládá se, že indexy P < Q < R < S <... pro prevPQ i pro nextPQ.</span><span class="sxs-lookup"><span data-stu-id="b03d9-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>