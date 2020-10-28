---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Operace PrepareChoiState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: 8b2917a7d9414539f2f7c821c4115fc4b21d0373
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708650"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="cdabe-102">Operace PrepareChoiState</span><span class="sxs-lookup"><span data-stu-id="cdabe-102">PrepareChoiState operation</span></span>

<span data-ttu-id="cdabe-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="cdabe-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="cdabe-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cdabe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cdabe-105">Připraví stav Choi – Jamiłkowski pro danou operaci na daný odkaz a cílové Registry.</span><span class="sxs-lookup"><span data-stu-id="cdabe-105">Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cdabe-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cdabe-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="cdabe-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cdabe-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cdabe-108">Operace $ \Lambda $, jejíž Choi – Jamiłkowski State $J (\Lambda)/2 ^ N $, se připravují, kde $N $ je počet qubits, na kterých `op` působí.</span><span class="sxs-lookup"><span data-stu-id="cdabe-108">Operation $\Lambda$ whose Choi–Jamiłkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="cdabe-109">Referenční informace: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cdabe-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cdabe-110">Registr qubits počínaje ve stavu $ \ket{00\cdots 0} $, který se má použít jako odkaz pro akci `op` .</span><span class="sxs-lookup"><span data-stu-id="cdabe-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="cdabe-111">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cdabe-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cdabe-112">Registr qubits zpočátku ve stavu $ \ket{00\cdots 0} $, ve kterém se má `op` použít.</span><span class="sxs-lookup"><span data-stu-id="cdabe-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cdabe-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cdabe-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cdabe-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="cdabe-114">Remarks</span></span>

<span data-ttu-id="cdabe-115">Choi – Jamiłkowski State $J (\Lambda) $ v procesu pro stav, který je definován jako $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ WHERE $ | X\rangle \! \rangle $ je *vektor* matice $X $ v konvenci pro skládání sloupců.</span><span class="sxs-lookup"><span data-stu-id="cdabe-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="cdabe-116">Výuková klasická Popis tohoto stavu poskytuje úplné informace o účinku $ \Lambda $ v libovolných vstupních stavech a tvoří základ pro *tomography procesu* .</span><span class="sxs-lookup"><span data-stu-id="cdabe-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography* .</span></span>

## <a name="see-also"></a><span data-ttu-id="cdabe-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="cdabe-117">See Also</span></span>

- [<span data-ttu-id="cdabe-118">Microsoft. Přípravno. Preparation. PrepareChoiStateA</span><span class="sxs-lookup"><span data-stu-id="cdabe-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="cdabe-119">Microsoft. Přípravno. Preparation. PrepareChoiStateC</span><span class="sxs-lookup"><span data-stu-id="cdabe-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="cdabe-120">Microsoft. Přípravno. Preparation. PrepareChoiStateCA</span><span class="sxs-lookup"><span data-stu-id="cdabe-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)