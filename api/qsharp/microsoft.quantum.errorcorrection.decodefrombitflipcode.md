---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: Operace DecodeFromBitFlipCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: b16e84340053b6c1eab7b91ed8db0461b9eac98e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827564"
---
# <a name="decodefrombitflipcode-operation"></a><span data-ttu-id="6c21a-102">Operace DecodeFromBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="6c21a-102">DecodeFromBitFlipCode operation</span></span>

<span data-ttu-id="6c21a-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="6c21a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="6c21a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6c21a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6c21a-105">Dekóduje z [3, 1, 3]/⟦ 3, 1, 1 ⟧ kódu překlopení.</span><span class="sxs-lookup"><span data-stu-id="6c21a-105">Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="6c21a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6c21a-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="6c21a-107">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="6c21a-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="6c21a-108">Blok kódu překlápění kódu.</span><span class="sxs-lookup"><span data-stu-id="6c21a-108">A code block of the bit-flip code.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="6c21a-109">Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="6c21a-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="6c21a-110">Řazená kolekce členů dat zakódovaných do logického registru a pomocné qubitsy, které slouží k reprezentaci Syndrome.</span><span class="sxs-lookup"><span data-stu-id="6c21a-110">A tuple of the data encoded into the logical register, and the auxiliary qubits used to represent the syndrome.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c21a-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="6c21a-111">See Also</span></span>

- [<span data-ttu-id="6c21a-112">Microsoft. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="6c21a-112">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="6c21a-113">Microsoft. ErrorCorrection. EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="6c21a-113">Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode</span></span>](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)