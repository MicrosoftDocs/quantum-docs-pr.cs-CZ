---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: Operace ApplyToPartition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: c1f43e7936fc1c18fb665388e9892dc3b74cdd05
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704728"
---
# <a name="applytopartition-operation"></a><span data-ttu-id="24ef2-102">Operace ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="24ef2-102">ApplyToPartition operation</span></span>

<span data-ttu-id="24ef2-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="24ef2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="24ef2-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="24ef2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="24ef2-105">Aplikuje dvojici operací na daný oddíl registru do dvou částí.</span><span class="sxs-lookup"><span data-stu-id="24ef2-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="24ef2-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="24ef2-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="24ef2-107">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24ef2-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="24ef2-108">Dvojice operací, které mají být pro daný oddíl aplikovány.</span><span class="sxs-lookup"><span data-stu-id="24ef2-108">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="24ef2-109">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="24ef2-109">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="24ef2-110">Počet qubits z cíle na vložení do první části oddílu</span><span class="sxs-lookup"><span data-stu-id="24ef2-110">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="24ef2-111">Zbývající qubits tvoří druhou část oddílu.</span><span class="sxs-lookup"><span data-stu-id="24ef2-111">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="24ef2-112">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="24ef2-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="24ef2-113">Registr qubitsů, které jsou rozděleny na oddíly a provozovány na základě dané dvě operace.</span><span class="sxs-lookup"><span data-stu-id="24ef2-113">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="24ef2-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24ef2-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="24ef2-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="24ef2-115">See Also</span></span>

- [<span data-ttu-id="24ef2-116">Microsoft. proApplyToPartitionA. Canon.</span><span class="sxs-lookup"><span data-stu-id="24ef2-116">Microsoft.Quantum.Canon.ApplyToPartitionA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [<span data-ttu-id="24ef2-117">Microsoft. proApplyToPartitionC. Canon.</span><span class="sxs-lookup"><span data-stu-id="24ef2-117">Microsoft.Quantum.Canon.ApplyToPartitionC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [<span data-ttu-id="24ef2-118">Microsoft. proApplyToPartitionCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="24ef2-118">Microsoft.Quantum.Canon.ApplyToPartitionCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)