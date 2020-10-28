---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: Operace EncodeIntoBitFlipCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697989"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="d3ce3-102">Operace EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="d3ce3-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="d3ce3-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="d3ce3-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="d3ce3-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3ce3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3ce3-105">Zakóduje do [3, 1, 3]/⟦ 3, 1, 1 ⟧ kódu překlopení.</span><span class="sxs-lookup"><span data-stu-id="d3ce3-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="d3ce3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d3ce3-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="d3ce3-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d3ce3-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d3ce3-108">Registr fyzických qubits představujících data, která mají být chráněna.</span><span class="sxs-lookup"><span data-stu-id="d3ce3-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="d3ce3-109">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d3ce3-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d3ce3-110">Registr pomocného qubits na začátku ve stavu $ \ket {00} $, který se má použít při kódování dat, která se mají chránit.</span><span class="sxs-lookup"><span data-stu-id="d3ce3-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="d3ce3-111">Výstup: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="d3ce3-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="d3ce3-112">Fyzický a pomocný qubits použitý v kódování, reprezentovaný jako logický registr.</span><span class="sxs-lookup"><span data-stu-id="d3ce3-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3ce3-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="d3ce3-113">See Also</span></span>

- [<span data-ttu-id="d3ce3-114">Microsoft. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="d3ce3-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)