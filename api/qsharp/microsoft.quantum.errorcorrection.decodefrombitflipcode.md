---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: Operace DecodeFromBitFlipCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: be6ad5fce9eeb3eea031ff301b78dbb3680b66f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698012"
---
# <a name="decodefrombitflipcode-operation"></a><span data-ttu-id="74b2b-102">Operace DecodeFromBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="74b2b-102">DecodeFromBitFlipCode operation</span></span>

<span data-ttu-id="74b2b-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="74b2b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="74b2b-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="74b2b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="74b2b-105">Dekóduje z [3, 1, 3]/⟦ 3, 1, 1 ⟧ kódu překlopení.</span><span class="sxs-lookup"><span data-stu-id="74b2b-105">Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="74b2b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="74b2b-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="74b2b-107">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="74b2b-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="74b2b-108">Blok kódu překlápění kódu.</span><span class="sxs-lookup"><span data-stu-id="74b2b-108">A code block of the bit-flip code.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="74b2b-109">Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="74b2b-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="74b2b-110">Řazená kolekce členů dat zakódovaných do logického registru a pomocné qubitsy, které slouží k reprezentaci Syndrome.</span><span class="sxs-lookup"><span data-stu-id="74b2b-110">A tuple of the data encoded into the logical register, and the auxiliary qubits used to represent the syndrome.</span></span>

## <a name="see-also"></a><span data-ttu-id="74b2b-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="74b2b-111">See Also</span></span>

- [<span data-ttu-id="74b2b-112">Microsoft. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="74b2b-112">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="74b2b-113">Microsoft. ErrorCorrection. EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="74b2b-113">Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode</span></span>](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)