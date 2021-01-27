---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Operace EncodeIntoFiveQubitCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 1bccf46453ad34199dcebc5bcff693359fe2254c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826319"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="f1c87-102">Operace EncodeIntoFiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="f1c87-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="f1c87-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f1c87-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f1c87-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1c87-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1c87-105">Se zakóduje do kódu ⟦ 5, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="f1c87-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="f1c87-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f1c87-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="f1c87-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f1c87-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f1c87-108">Qubit představující nekódovaný stav.</span><span class="sxs-lookup"><span data-stu-id="f1c87-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="f1c87-109">Toto pole `Qubit[]` má délku 1.</span><span class="sxs-lookup"><span data-stu-id="f1c87-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="f1c87-110">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f1c87-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f1c87-111">Registr pomocných qubitsů, které se budou používat k reprezentování kódovaného stavu.</span><span class="sxs-lookup"><span data-stu-id="f1c87-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="f1c87-112">Výstup: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="f1c87-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="f1c87-113">Pole fyzického qubits typu `LogicalRegister` , které ukládá kódovaný stav.</span><span class="sxs-lookup"><span data-stu-id="f1c87-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1c87-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="f1c87-114">See Also</span></span>

- [<span data-ttu-id="f1c87-115">Microsoft. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="f1c87-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)