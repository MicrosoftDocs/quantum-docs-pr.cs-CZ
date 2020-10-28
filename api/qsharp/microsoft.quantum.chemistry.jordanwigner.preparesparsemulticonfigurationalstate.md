---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: Operace PrepareSparseMultiConfigurationalState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 1182f79a33784cdb49cb13db5cc97a0a45e59f9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698401"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a><span data-ttu-id="6bf59-102">Operace PrepareSparseMultiConfigurationalState</span><span class="sxs-lookup"><span data-stu-id="6bf59-102">PrepareSparseMultiConfigurationalState operation</span></span>

<span data-ttu-id="6bf59-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="6bf59-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="6bf59-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6bf59-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6bf59-105">Příprava zkušebního stavu s více konfiguračními stavy přidáním excitations do počátečního stavu zkušební verze.</span><span class="sxs-lookup"><span data-stu-id="6bf59-105">Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.</span></span>

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6bf59-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6bf59-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="6bf59-107">initialStatePreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6bf59-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6bf59-108">Pro přípravu počátečního stavu zkušební verze se jedná o jednotnou.</span><span class="sxs-lookup"><span data-stu-id="6bf59-108">Unitary to prepare initial trial state.</span></span>


### <a name="excitations--jordanwignerinputstate"></a><span data-ttu-id="6bf59-109">excitations: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="6bf59-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="6bf59-110">Excitations počátečního zkušebního stavu reprezentovaného amplitudou excitation a qubit indexy, na kterých excitation funguje.</span><span class="sxs-lookup"><span data-stu-id="6bf59-110">Excitations of initial trial state represented by the amplitude of the excitation and the qubit indices the excitation acts on.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="6bf59-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6bf59-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6bf59-112">Qubits z Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="6bf59-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6bf59-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6bf59-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

