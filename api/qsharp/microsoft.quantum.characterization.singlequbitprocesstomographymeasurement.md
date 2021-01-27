---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: Operace SingleQubitProcessTomographyMeasurement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 883b98ad4f2d0ac4a02e55e444c04e8e7cf37af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839640"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="114c6-102">Operace SingleQubitProcessTomographyMeasurement</span><span class="sxs-lookup"><span data-stu-id="114c6-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="114c6-103">Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="114c6-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="114c6-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="114c6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="114c6-105">Provede qubit proces tomography měření v Pauli, a to s ohledem na konkrétní kanál zájmu.</span><span class="sxs-lookup"><span data-stu-id="114c6-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="114c6-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="114c6-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="114c6-107">Příprava: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="114c6-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="114c6-108">Základní element Pauli $P $, ve kterém má být připraven qubit.</span><span class="sxs-lookup"><span data-stu-id="114c6-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="114c6-109">měření: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="114c6-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="114c6-110">Základní element Pauli $Q $, ve kterém se má měřit qubit.</span><span class="sxs-lookup"><span data-stu-id="114c6-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="114c6-111">kanál: [](xref:microsoft.quantum.lang-ref.qubit) => [jednotka](xref:microsoft.quantum.lang-ref.unit) qubit</span><span class="sxs-lookup"><span data-stu-id="114c6-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="114c6-112">Jeden qubit kanál $ \Lambda $, jehož chování se odhaduje pomocí procesu tomography.</span><span class="sxs-lookup"><span data-stu-id="114c6-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="114c6-113">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="114c6-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="114c6-114">Výsledek `Zero` s pravděpodobností $ $ \Begin{align} \Pr (\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).</span><span class="sxs-lookup"><span data-stu-id="114c6-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="114c6-115">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="114c6-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="114c6-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="114c6-116">Remarks</span></span>

<span data-ttu-id="114c6-117">Distribuce výsledků vrácená touto operací je zvláštní případ qubit tomography stavu.</span><span class="sxs-lookup"><span data-stu-id="114c6-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="114c6-118">Nechť $ \rho = J (\Lambda)/$2 být stav Choi – Jamiłkowski pro $ \Lambda $.</span><span class="sxs-lookup"><span data-stu-id="114c6-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="114c6-119">Výše uvedená distribuce je stejná jako u $ $ \begin{align} \Pr (\texttt{Zero} | \rho; M) = \operatorname{Tr} (M \rho); \end{align} $ $ WHERE $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 je efektivní měření odpovídající $P $ a $Q $.</span><span class="sxs-lookup"><span data-stu-id="114c6-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>