---
uid: Microsoft.Quantum.Intrinsic.R
title: Operace R
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 7d1d51031f4587b1c501feab459e614fc1530457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707152"
---
# <a name="r-operation"></a><span data-ttu-id="05db5-102">Operace R</span><span class="sxs-lookup"><span data-stu-id="05db5-102">R operation</span></span>

<span data-ttu-id="05db5-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="05db5-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="05db5-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05db5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05db5-105">Použije rotaci o dané ose Pauli.</span><span class="sxs-lookup"><span data-stu-id="05db5-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="05db5-106">\begin{align} R_ {\mu} (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_ {\mu}/2}, \end{align} WHERE $ \mu \in \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="05db5-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="05db5-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="05db5-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="05db5-108">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="05db5-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="05db5-109">Pauli – operátor ($ \mu $), který bude exponentiated pro vytvoření rotace.</span><span class="sxs-lookup"><span data-stu-id="05db5-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="05db5-110">théta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="05db5-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="05db5-111">Úhel, o který se má qubit otočit</span><span class="sxs-lookup"><span data-stu-id="05db5-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="05db5-112">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="05db5-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="05db5-113">Qubit, na který se má brána použít</span><span class="sxs-lookup"><span data-stu-id="05db5-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="05db5-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05db5-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="05db5-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="05db5-115">Remarks</span></span>

<span data-ttu-id="05db5-116">Při volání s se `pauli = PauliI` Tato operace vztahuje na *globální fázi* .</span><span class="sxs-lookup"><span data-stu-id="05db5-116">When called with `pauli = PauliI`, this operation applies a *global phase* .</span></span> <span data-ttu-id="05db5-117">Tato fáze může být při použití s funktor významná `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="05db5-117">This phase can be significant when used with the `Controlled` functor.</span></span>