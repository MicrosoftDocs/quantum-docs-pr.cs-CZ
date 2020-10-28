---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: Operace MeasureStabilizerGenerators
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697949"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="908dd-102">Operace MeasureStabilizerGenerators</span><span class="sxs-lookup"><span data-stu-id="908dd-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="908dd-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="908dd-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="908dd-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="908dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="908dd-105">Měří danou sadu generátorů skupiny stabilizace.</span><span class="sxs-lookup"><span data-stu-id="908dd-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="908dd-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="908dd-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="908dd-107">stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="908dd-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="908dd-108">Pole operátorů Pauli multiqubit</span><span class="sxs-lookup"><span data-stu-id="908dd-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="908dd-109">Například `stabilizerGroup[0]` je seznam matic qubit Pauli, což je tensor produkt, který je generátorem stabilizace.</span><span class="sxs-lookup"><span data-stu-id="908dd-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="908dd-110">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="908dd-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="908dd-111">Pole qubits, kde je definován kód stabilizace.</span><span class="sxs-lookup"><span data-stu-id="908dd-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="908dd-112">gadget: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]; [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="908dd-112">gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="908dd-113">Operace, která určuje, jak změřit multiqubit Pauli operátor.</span><span class="sxs-lookup"><span data-stu-id="908dd-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="908dd-114">Výstup: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="908dd-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="908dd-115">Výsledek měření</span><span class="sxs-lookup"><span data-stu-id="908dd-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="908dd-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="908dd-116">Remarks</span></span>

<span data-ttu-id="908dd-117">Tato nekontroluje, zda daná sada generátorů dokončí dojíždění.</span><span class="sxs-lookup"><span data-stu-id="908dd-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="908dd-118">Pokud se dostanou, výsledek měření může být libovolný.</span><span class="sxs-lookup"><span data-stu-id="908dd-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>