---
uid: Microsoft.Quantum.Intrinsic.R
title: Operace R
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 89aa5b2867068d4352a0b9550e8d22aa77439111
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199025"
---
# <a name="r-operation"></a><span data-ttu-id="1c471-102">Operace R</span><span class="sxs-lookup"><span data-stu-id="1c471-102">R operation</span></span>

<span data-ttu-id="1c471-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="1c471-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="1c471-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1c471-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1c471-105">Použije rotaci o dané ose Pauli.</span><span class="sxs-lookup"><span data-stu-id="1c471-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="1c471-106">\begin{align} R_ {\mu} (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_ {\mu}/2}, \end{align} WHERE $ \mu \in \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="1c471-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1c471-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="1c471-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="1c471-108">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="1c471-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="1c471-109">Pauli – operátor ($ \mu $), který bude exponentiated pro vytvoření rotace.</span><span class="sxs-lookup"><span data-stu-id="1c471-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="1c471-110">théta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1c471-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1c471-111">Úhel, o který se má qubit otočit</span><span class="sxs-lookup"><span data-stu-id="1c471-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="1c471-112">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1c471-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1c471-113">Qubit, na který se má brána použít</span><span class="sxs-lookup"><span data-stu-id="1c471-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1c471-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c471-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1c471-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="1c471-115">Remarks</span></span>

<span data-ttu-id="1c471-116">Při volání s se `pauli = PauliI` Tato operace vztahuje na *globální fázi*.</span><span class="sxs-lookup"><span data-stu-id="1c471-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="1c471-117">Tato fáze může být při použití s funktor významná `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="1c471-117">This phase can be significant when used with the `Controlled` functor.</span></span>