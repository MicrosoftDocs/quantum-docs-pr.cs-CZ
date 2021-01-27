---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Operace PrepareChoiState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: cb34078c09f8c28b5b9bbda1bae6936d13ffcc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854406"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="999b2-102">Operace PrepareChoiState</span><span class="sxs-lookup"><span data-stu-id="999b2-102">PrepareChoiState operation</span></span>

<span data-ttu-id="999b2-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="999b2-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="999b2-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="999b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="999b2-105">Připraví stav Choi – Jamiołkowski pro danou operaci na daný odkaz a cílové Registry.</span><span class="sxs-lookup"><span data-stu-id="999b2-105">Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="999b2-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="999b2-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="999b2-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="999b2-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="999b2-108">Operace $ \Lambda $, jejíž Choi – Jamiołkowski State $J (\Lambda)/2 ^ N $, se připravují, kde $N $ je počet qubits, na kterých `op` působí.</span><span class="sxs-lookup"><span data-stu-id="999b2-108">Operation $\Lambda$ whose Choi–Jamiołkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="999b2-109">Referenční informace: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="999b2-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="999b2-110">Registr qubits počínaje ve stavu $ \ket{00\cdots 0} $, který se má použít jako odkaz pro akci `op` .</span><span class="sxs-lookup"><span data-stu-id="999b2-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="999b2-111">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="999b2-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="999b2-112">Registr qubits zpočátku ve stavu $ \ket{00\cdots 0} $, ve kterém se má `op` použít.</span><span class="sxs-lookup"><span data-stu-id="999b2-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="999b2-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="999b2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="999b2-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="999b2-114">Remarks</span></span>

<span data-ttu-id="999b2-115">Choi – Jamiłkowski State $J (\Lambda) $ v procesu pro stav, který je definován jako $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ WHERE $ | X\rangle \! \rangle $ je *vektor* matice $X $ v konvenci pro skládání sloupců.</span><span class="sxs-lookup"><span data-stu-id="999b2-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="999b2-116">Výuková klasická Popis tohoto stavu poskytuje úplné informace o účinku $ \Lambda $ v libovolných vstupních stavech a tvoří základ pro *tomography procesu*.</span><span class="sxs-lookup"><span data-stu-id="999b2-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography*.</span></span>

## <a name="see-also"></a><span data-ttu-id="999b2-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="999b2-117">See Also</span></span>

- [<span data-ttu-id="999b2-118">Microsoft. Přípravno. Preparation. PrepareChoiStateA</span><span class="sxs-lookup"><span data-stu-id="999b2-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="999b2-119">Microsoft. Přípravno. Preparation. PrepareChoiStateC</span><span class="sxs-lookup"><span data-stu-id="999b2-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="999b2-120">Microsoft. Přípravno. Preparation. PrepareChoiStateCA</span><span class="sxs-lookup"><span data-stu-id="999b2-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)