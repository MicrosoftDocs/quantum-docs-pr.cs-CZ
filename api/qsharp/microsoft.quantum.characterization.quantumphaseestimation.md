---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: Operace QuantumPhaseEstimation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 4bdf3de9dab20fa97ba47f15efec4b41a10709f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839657"
---
# <a name="quantumphaseestimation-operation"></a><span data-ttu-id="191cd-102">Operace QuantumPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="191cd-102">QuantumPhaseEstimation operation</span></span>

<span data-ttu-id="191cd-103">Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="191cd-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="191cd-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="191cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="191cd-105">Provádí pro daný Oracle algoritmus odhadu doby přírůstku `U` a `targetState` přečtení fáze do pokladny na základě služby big-endian.</span><span class="sxs-lookup"><span data-stu-id="191cd-105">Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.</span></span>

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="191cd-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="191cd-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="191cd-107">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="191cd-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="191cd-108">Operace implementující $U ^ m $ pro celou celočíselnou mocninu m.</span><span class="sxs-lookup"><span data-stu-id="191cd-108">An operation implementing $U^m$ for given integer powers m.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="191cd-109">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="191cd-109">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="191cd-110">Registr u, který představuje stav $ \ket{\phi} $, se v $U $.</span><span class="sxs-lookup"><span data-stu-id="191cd-110">A quantum register representing the state $\ket{\phi}$ acted on by $U$.</span></span> <span data-ttu-id="191cd-111">Pokud $ \ket{\phi} $ je eigenstate z $U $, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \phi \in [0, 2 \ pi) $ je neznámá fáze.</span><span class="sxs-lookup"><span data-stu-id="191cd-111">If $\ket{\phi}$ is an eigenstate of $U$, $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi \in [0, 2\pi)$ an unknown phase.</span></span>


### <a name="controlregister--bigendian"></a><span data-ttu-id="191cd-112">controlRegister: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="191cd-112">controlRegister : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="191cd-113">Registr s celočíselnými vyjádřeními big-endian, který se dá použít k řízení poskytnutého Oracle a který bude obsahovat reprezentaci $ \phi $ za použití této operace.</span><span class="sxs-lookup"><span data-stu-id="191cd-113">A big-endian representation integer register that can be used to control the provided oracle, and that will contain the a representation of $\phi$ following the application of this operation.</span></span> <span data-ttu-id="191cd-114">Předpokládá se, že controlRegister začíná v počátečním stavu $ \ket{00\cdots 0} $, kde délka registru označuje požadovanou přesnost.</span><span class="sxs-lookup"><span data-stu-id="191cd-114">The controlRegister is assumed to start in the initial state $\ket{00\cdots 0}$, where the length of the register indicates the desired precision.</span></span>



## <a name="output--unit"></a><span data-ttu-id="191cd-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="191cd-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

