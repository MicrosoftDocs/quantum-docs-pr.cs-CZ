---
uid: Microsoft.Quantum.Canon.ApplyToPartitionA
title: Operace ApplyToPartitionA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 6ff3bf8b5a4344ee5a7a054c6285a5492260068d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704720"
---
# <a name="applytopartitiona-operation"></a><span data-ttu-id="0d9fa-102">Operace ApplyToPartitionA</span><span class="sxs-lookup"><span data-stu-id="0d9fa-102">ApplyToPartitionA operation</span></span>

<span data-ttu-id="0d9fa-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0d9fa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0d9fa-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d9fa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0d9fa-105">Aplikuje dvojici operací na daný oddíl registru do dvou částí.</span><span class="sxs-lookup"><span data-stu-id="0d9fa-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="0d9fa-106">Modifikátor `A` označuje, že operace je sousední.</span><span class="sxs-lookup"><span data-stu-id="0d9fa-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToPartitionA (op : ((Qubit[], Qubit[]) => Unit is Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0d9fa-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="0d9fa-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj"></a><span data-ttu-id="0d9fa-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="0d9fa-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="0d9fa-109">Dvojice operací, které mají být pro daný oddíl aplikovány.</span><span class="sxs-lookup"><span data-stu-id="0d9fa-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="0d9fa-110">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0d9fa-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0d9fa-111">Počet qubits z cíle na vložení do první části oddílu</span><span class="sxs-lookup"><span data-stu-id="0d9fa-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="0d9fa-112">Zbývající qubits tvoří druhou část oddílu.</span><span class="sxs-lookup"><span data-stu-id="0d9fa-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="0d9fa-113">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0d9fa-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0d9fa-114">Registr qubitsů, které jsou rozděleny na oddíly a provozovány na základě dané dvě operace.</span><span class="sxs-lookup"><span data-stu-id="0d9fa-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0d9fa-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d9fa-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0d9fa-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="0d9fa-116">See Also</span></span>

- [<span data-ttu-id="0d9fa-117">Microsoft. proApplyToPartition. Canon.</span><span class="sxs-lookup"><span data-stu-id="0d9fa-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)