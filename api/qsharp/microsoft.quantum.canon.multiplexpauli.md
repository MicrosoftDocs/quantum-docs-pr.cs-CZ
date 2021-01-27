---
uid: Microsoft.Quantum.Canon.MultiplexPauli
title: Operace MultiplexPauli
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits.
ms.openlocfilehash: 656b510cb19af69a9a3f0d537d54b0abfe76de4b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852451"
---
# <a name="multiplexpauli-operation"></a><span data-ttu-id="80259-102">Operace MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="80259-102">MultiplexPauli operation</span></span>

<span data-ttu-id="80259-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="80259-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="80259-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80259-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80259-105">Použije Pauli rotaci v poli qubits.</span><span class="sxs-lookup"><span data-stu-id="80259-105">Applies a Pauli rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexPauli (coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="80259-106">Popis</span><span class="sxs-lookup"><span data-stu-id="80259-106">Description</span></span>

<span data-ttu-id="80259-107">To platí pro násobenou jednotnou operaci, která provádí rotace pomocí úhlu $ \ theta_j $ o qubit Pauli operator $P $, pokud je kontrolováno stavem $n $-qubit číslo $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="80259-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="80259-108">Konkrétně se akce této operace reprezentuje jednotně.</span><span class="sxs-lookup"><span data-stu-id="80259-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="80259-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="80259-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="80259-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="80259-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="80259-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="80259-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="80259-112">koeficienty: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="80259-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="80259-113">Pole až do $2 ^ n $ koeficienty $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="80259-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="80259-114">$J $ th součinitel indexuje číselný stav $ \ket{j} $ kódovaný ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="80259-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="80259-115">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="80259-115">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="80259-116">Pauli operátor $P $, který určuje osu otočení.</span><span class="sxs-lookup"><span data-stu-id="80259-116">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="80259-117">ovládací prvek: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="80259-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="80259-118">$n $-qubit registr ovládacího prvku, který kóduje číselný stav $ \ket{j} $ ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="80259-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="80259-119">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="80259-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="80259-120">Jeden qubit registr, který je otočen $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="80259-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80259-121">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80259-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="80259-122">Poznámky</span><span class="sxs-lookup"><span data-stu-id="80259-122">Remarks</span></span>

<span data-ttu-id="80259-123">`coefficients` budou doplněny elementy $ \ theta_j = $0,0, pokud je zadána méně než $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="80259-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="80259-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="80259-124">See Also</span></span>

- [<span data-ttu-id="80259-125">Microsoft. proApproximatelyMultiplexPauli. Canon.</span><span class="sxs-lookup"><span data-stu-id="80259-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli)