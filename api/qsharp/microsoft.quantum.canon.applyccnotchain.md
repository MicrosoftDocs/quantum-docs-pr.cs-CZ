---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: Operace ApplyCCNOTChain
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: e4f38e9bb54839076b817f6e61e96ca6a550576b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705456"
---
# <a name="applyccnotchain-operation"></a><span data-ttu-id="21563-102">Operace ApplyCCNOTChain</span><span class="sxs-lookup"><span data-stu-id="21563-102">ApplyCCNOTChain operation</span></span>

<span data-ttu-id="21563-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="21563-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="21563-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="21563-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="21563-105">Implementuje kaskády CCNOTch bran řízených v odpovídajících bitech dvou registrů qubit, které fungují na dalších qubit jednoho z registrů.</span><span class="sxs-lookup"><span data-stu-id="21563-105">Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers.</span></span>
<span data-ttu-id="21563-106">Počínaje od qubits na pozici 0 v obou registrech jako ovládací prvky se CCNOT použije na qubit na pozici 1 cílového registru, kterou řídí qubits na pozici 1 v qubit na pozici 2 v cílovém registru atd., končící akci na cílovém qubit na pozici `Length(nQubits)-1` .</span><span class="sxs-lookup"><span data-stu-id="21563-106">Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.</span></span>

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="21563-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="21563-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="21563-108">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="21563-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="21563-109">Qubit registr, používá se pouze pro ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="21563-109">Qubit register, only used for controls.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="21563-110">cíle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="21563-110">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="21563-111">Qubit registr, který se používá pro ovládací prvky a jako cíl.</span><span class="sxs-lookup"><span data-stu-id="21563-111">Qubit register, used for controls and as target.</span></span>



## <a name="output--unit"></a><span data-ttu-id="21563-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="21563-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="21563-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="21563-113">Remarks</span></span>

<span data-ttu-id="21563-114">Cílový registr qubit musí mít jeden qubit více než druhý registr.</span><span class="sxs-lookup"><span data-stu-id="21563-114">The target qubit register must have one qubit more than the other register.</span></span>