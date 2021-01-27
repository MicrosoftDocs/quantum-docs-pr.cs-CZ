---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: Operace _ExtractLogicalQubitFromSteaneCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: fe64343e30a0a3f0d05382e7812d37d5b13133d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853217"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a><span data-ttu-id="b76fc-102">Operace _ExtractLogicalQubitFromSteaneCode</span><span class="sxs-lookup"><span data-stu-id="b76fc-102">_ExtractLogicalQubitFromSteaneCode operation</span></span>

<span data-ttu-id="b76fc-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="b76fc-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="b76fc-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b76fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b76fc-105">Syndrome měření a inverzní funkce pro vkládání.</span><span class="sxs-lookup"><span data-stu-id="b76fc-105">Syndrome measurement and the inverse of embedding.</span></span>

<span data-ttu-id="b76fc-106">$X $-a $Z $-stabilizátory se nepovažují za stejné, což je kvůli konkrétní volbě okruhu kódování.</span><span class="sxs-lookup"><span data-stu-id="b76fc-106">$X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit.</span></span>
<span data-ttu-id="b76fc-107">Tato asymetrie vede k jiné rutině extrakce Syndrome.</span><span class="sxs-lookup"><span data-stu-id="b76fc-107">This asymmetry leads to a different syndrome extraction routine.</span></span>
<span data-ttu-id="b76fc-108">Jedním z nich může změřit Syndrome pomocí měření qubit Pauli operátora přímo ve stavu kódu, ale pro účely destilace se logické qubit vrátí do jednoho qubit, v případě, že se Syndrome měření dá provést bez dalšího ancillas.</span><span class="sxs-lookup"><span data-stu-id="b76fc-108">One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.</span></span>

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a><span data-ttu-id="b76fc-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="b76fc-109">Input</span></span>

### <a name="code--logicalregister"></a><span data-ttu-id="b76fc-110">kód: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="b76fc-110">code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>





## <a name="output--qubitintint"></a><span data-ttu-id="b76fc-111">Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="b76fc-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="b76fc-112">Logický qubit a dvojice celých čísel pro $X $-Syndrome a $Z $-Syndrome.</span><span class="sxs-lookup"><span data-stu-id="b76fc-112">The logical qubit and a pair of integers for $X$-syndrome and $Z$-syndrome.</span></span>
<span data-ttu-id="b76fc-113">Představují index qubit kódu, na kterém by jedna $X $-nebo $Z $-Error způsobila měřený Syndrome.</span><span class="sxs-lookup"><span data-stu-id="b76fc-113">They represent the index of the code qubit on which a single $X$- or $Z$-error would have caused the measured syndrome.</span></span>

## <a name="remarks"></a><span data-ttu-id="b76fc-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b76fc-114">Remarks</span></span>

<span data-ttu-id="b76fc-115">Všimněte si, že tato operace není označena jako `internal` , protože testy jednotek přímo závisejí na této operaci.</span><span class="sxs-lookup"><span data-stu-id="b76fc-115">Note that this operation is not marked as `internal`, as unit tests directly depend on this operation.</span></span> <span data-ttu-id="b76fc-116">V rámci budoucího zlepšení by testy jednotek měly být refaktorované, aby závislé jenom na veřejných volatcích.</span><span class="sxs-lookup"><span data-stu-id="b76fc-116">As a future improvement, unit tests should be refactored to depend only on public callables directly.</span></span>

> [!WARNING]
> <span data-ttu-id="b76fc-117">Tato rutina je přizpůsobená konkrétnímu okruhu kódování pro qubit kód Steane. Pokud se změní okruh kódování, může být výsledek Syndrome vyhodnocen jinak.</span><span class="sxs-lookup"><span data-stu-id="b76fc-117">This routine is tailored to a particular encoding circuit for Steane's 7 qubit code; if the encoding circuit is modified then the syndrome outcome might have to be interpreted differently.</span></span>