---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: Operace ApplyMultiplyControlledLowDepthAnd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 6900f9b0f014fba28ae73a70f180f3e4696900cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705185"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="029bb-102">Operace ApplyMultiplyControlledLowDepthAnd</span><span class="sxs-lookup"><span data-stu-id="029bb-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="029bb-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="029bb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="029bb-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="029bb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="029bb-105">Implementuje Toffoli bránu s více řízenými hodnotami za předpokladu, že cílový qubit je inicializovaný 0.</span><span class="sxs-lookup"><span data-stu-id="029bb-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="029bb-106">Operace souseda předpokládá, že cílový qubit bude resetován na hodnotu 0.</span><span class="sxs-lookup"><span data-stu-id="029bb-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="029bb-107">Vyžaduje RZ hloubku 1, zatímco počet pomocných qubits je exponenciální v počtu qubits.</span><span class="sxs-lookup"><span data-stu-id="029bb-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="029bb-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="029bb-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="029bb-109">ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="029bb-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="029bb-110">Qubits ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="029bb-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="029bb-111">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="029bb-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="029bb-112">Cílový qubit</span><span class="sxs-lookup"><span data-stu-id="029bb-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="029bb-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="029bb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

