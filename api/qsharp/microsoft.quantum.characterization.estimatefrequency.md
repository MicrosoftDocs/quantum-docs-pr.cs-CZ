---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: Operace EstimateFrequency
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 1e044a08718e02d673edab1d6b9d16d7f09618dc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851881"
---
# <a name="estimatefrequency-operation"></a><span data-ttu-id="d9cc1-102">Operace EstimateFrequency</span><span class="sxs-lookup"><span data-stu-id="d9cc1-102">EstimateFrequency operation</span></span>

<span data-ttu-id="d9cc1-103">Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="d9cc1-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="d9cc1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9cc1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9cc1-105">S ohledem na přípravu a měření odhadne četnost, s jakou měření `Zero` probíhají (vrátí), provedením daného počtu testů.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-105">Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="d9cc1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d9cc1-106">Input</span></span>

### <a name="preparation--qubit--unit"></a><span data-ttu-id="d9cc1-107">Příprava: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9cc1-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d9cc1-108">Operace $P $, která ve svém vstupním registru připraví daný stav $ \rho $.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-108">An operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="d9cc1-109">měření: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="d9cc1-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="d9cc1-110">Operace $M $ představuje měření zájmu.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="d9cc1-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d9cc1-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d9cc1-112">Počet qubits, na které se každý působí přípravek a měření.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="d9cc1-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d9cc1-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d9cc1-114">Počet, kolikrát by měla být provedena měření, aby se mohla odhadnout frekvence zájmu.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="d9cc1-115">Výstup: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d9cc1-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d9cc1-116">Odhad $ \hat{p} $ frekvence, se kterou $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ vrátí `Zero` , získaný pomocí nevyváženého binomického Estimator $ \hat{p} = n \_ {\uparrow}/n \_ {\Text{Measurements}} $, kde $n \_ {\uparrow} $ je počet `Zero` zjištěných výsledků.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

<span data-ttu-id="d9cc1-117">To je důležité zejména u cílových počítačů, které jsou v souladu s fyzickými omezeními, což znamená, že pravděpodobnosti nelze změřit.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-117">This is particularly important on target machines which respect physical limitations, such that probabilities cannot be measured.</span></span>