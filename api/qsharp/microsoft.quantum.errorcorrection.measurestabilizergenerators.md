---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: Operace MeasureStabilizerGenerators
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: 6c048c17df21d1026dc671f30d72a13ed8d8b7f5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200624"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="4f350-102">Operace MeasureStabilizerGenerators</span><span class="sxs-lookup"><span data-stu-id="4f350-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="4f350-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="4f350-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="4f350-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f350-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f350-105">Měří danou sadu generátorů skupiny stabilizace.</span><span class="sxs-lookup"><span data-stu-id="4f350-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="4f350-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4f350-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="4f350-107">stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="4f350-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="4f350-108">Pole operátorů Pauli multiqubit</span><span class="sxs-lookup"><span data-stu-id="4f350-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="4f350-109">Například `stabilizerGroup[0]` je seznam matic qubit Pauli, což je tensor produkt, který je generátorem stabilizace.</span><span class="sxs-lookup"><span data-stu-id="4f350-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="4f350-110">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="4f350-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="4f350-111">Pole qubits, kde je definován kód stabilizace.</span><span class="sxs-lookup"><span data-stu-id="4f350-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="4f350-112">gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="4f350-112">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="4f350-113">Operace, která určuje, jak změřit multiqubit Pauli operátor.</span><span class="sxs-lookup"><span data-stu-id="4f350-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="4f350-114">Výstup: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="4f350-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="4f350-115">Výsledek měření</span><span class="sxs-lookup"><span data-stu-id="4f350-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f350-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4f350-116">Remarks</span></span>

<span data-ttu-id="4f350-117">Tato nekontroluje, zda daná sada generátorů dokončí dojíždění.</span><span class="sxs-lookup"><span data-stu-id="4f350-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="4f350-118">Pokud se dostanou, výsledek měření může být libovolný.</span><span class="sxs-lookup"><span data-stu-id="4f350-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>