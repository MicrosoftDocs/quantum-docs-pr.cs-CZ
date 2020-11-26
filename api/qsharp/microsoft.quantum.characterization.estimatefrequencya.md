---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: Operace EstimateFrequencyA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: f12fc150de5bcea3d53ce88003c71976d8f2467f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204347"
---
# <a name="estimatefrequencya-operation"></a><span data-ttu-id="dd4f5-102">Operace EstimateFrequencyA</span><span class="sxs-lookup"><span data-stu-id="dd4f5-102">EstimateFrequencyA operation</span></span>

<span data-ttu-id="dd4f5-103">Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="dd4f5-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="dd4f5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd4f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd4f5-105">S ohledem na přípravu, která je sousední a měření, odhadne četnost, s jakou měření vychází (vrátí `Zero` ) provedením daného počtu zkušebních hodnot.</span><span class="sxs-lookup"><span data-stu-id="dd4f5-105">Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="dd4f5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="dd4f5-106">Input</span></span>

### <a name="preparation--qubit--unit--is-adj"></a><span data-ttu-id="dd4f5-107">Příprava: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="dd4f5-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="dd4f5-108">Operace s sousedícím objektem $P $, která připraví daný stav $ \rho $ na vstupním registru.</span><span class="sxs-lookup"><span data-stu-id="dd4f5-108">An adjointable operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="dd4f5-109">měření: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="dd4f5-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="dd4f5-110">Operace $M $ představuje měření zájmu.</span><span class="sxs-lookup"><span data-stu-id="dd4f5-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="dd4f5-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd4f5-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd4f5-112">Počet qubits, na které se každý působí přípravek a měření.</span><span class="sxs-lookup"><span data-stu-id="dd4f5-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="dd4f5-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd4f5-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd4f5-114">Počet, kolikrát by měla být provedena měření, aby se mohla odhadnout frekvence zájmu.</span><span class="sxs-lookup"><span data-stu-id="dd4f5-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="dd4f5-115">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dd4f5-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dd4f5-116">Odhad $ \hat{p} $ frekvence, se kterou $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ vrátí `Zero` , získaný pomocí nevyváženého binomického Estimator $ \hat{p} = n \_ {\uparrow}/n \_ {\Text{Measurements}} $, kde $n \_ {\uparrow} $ je počet `Zero` zjištěných výsledků.</span><span class="sxs-lookup"><span data-stu-id="dd4f5-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd4f5-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="dd4f5-117">Remarks</span></span>

<span data-ttu-id="dd4f5-118">U sousedních operací lze určit určité předpoklady, jako je například volání operace, připraví qubits na přesně stejný stav, což umožňuje cílovým počítačům provádět některé optimalizace výkonu.</span><span class="sxs-lookup"><span data-stu-id="dd4f5-118">For adjointable operations, certain assumptions can be made such like calling the operation will prepare the qubits to exactly the same state, which allow target machines to make some performance optimizations.</span></span>