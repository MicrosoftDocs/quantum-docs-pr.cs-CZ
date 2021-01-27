---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: Operace EncodeIntoBitFlipCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 44034a864c946a7d3dbb21bad5ee500660709f1a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826679"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="195a7-102">Operace EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="195a7-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="195a7-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="195a7-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="195a7-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="195a7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="195a7-105">Zakóduje do [3, 1, 3]/⟦ 3, 1, 1 ⟧ kódu překlopení.</span><span class="sxs-lookup"><span data-stu-id="195a7-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="195a7-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="195a7-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="195a7-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="195a7-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="195a7-108">Registr fyzických qubits představujících data, která mají být chráněna.</span><span class="sxs-lookup"><span data-stu-id="195a7-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="195a7-109">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="195a7-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="195a7-110">Registr pomocného qubits na začátku ve stavu $ \ket {00} $, který se má použít při kódování dat, která se mají chránit.</span><span class="sxs-lookup"><span data-stu-id="195a7-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="195a7-111">Výstup: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="195a7-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="195a7-112">Fyzický a pomocný qubits použitý v kódování, reprezentovaný jako logický registr.</span><span class="sxs-lookup"><span data-stu-id="195a7-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="195a7-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="195a7-113">See Also</span></span>

- [<span data-ttu-id="195a7-114">Microsoft. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="195a7-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)