---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: Operace ApplyMultiplyControlledLowDepthAnd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 1aeab429bd6304c621e0d5225b43a76eab607c84
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209192"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="33cbc-102">Operace ApplyMultiplyControlledLowDepthAnd</span><span class="sxs-lookup"><span data-stu-id="33cbc-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="33cbc-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="33cbc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="33cbc-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="33cbc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="33cbc-105">Implementuje Toffoli bránu s více řízenými hodnotami za předpokladu, že cílový qubit je inicializovaný 0.</span><span class="sxs-lookup"><span data-stu-id="33cbc-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="33cbc-106">Operace souseda předpokládá, že cílový qubit bude resetován na hodnotu 0.</span><span class="sxs-lookup"><span data-stu-id="33cbc-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="33cbc-107">Vyžaduje RZ hloubku 1, zatímco počet pomocných qubits je exponenciální v počtu qubits.</span><span class="sxs-lookup"><span data-stu-id="33cbc-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="33cbc-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="33cbc-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="33cbc-109">ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="33cbc-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="33cbc-110">Qubits ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="33cbc-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="33cbc-111">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="33cbc-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="33cbc-112">Cílový qubit</span><span class="sxs-lookup"><span data-stu-id="33cbc-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="33cbc-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33cbc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

