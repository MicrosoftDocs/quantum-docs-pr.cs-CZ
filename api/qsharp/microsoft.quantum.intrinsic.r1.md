---
uid: Microsoft.Quantum.Intrinsic.R1
title: Operace R1
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: 07cce580b50fef5664fdac32bb4fae0ba22d25e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849353"
---
# <a name="r1-operation"></a><span data-ttu-id="ca8cd-102">Operace R1</span><span class="sxs-lookup"><span data-stu-id="ca8cd-102">R1 operation</span></span>

<span data-ttu-id="ca8cd-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ca8cd-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ca8cd-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ca8cd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ca8cd-105">Použije rotaci o stavu $ \ket {1} $ podle daného úhlu.</span><span class="sxs-lookup"><span data-stu-id="ca8cd-105">Applies a rotation about the $\ket{1}$ state by a given angle.</span></span>

<span data-ttu-id="ca8cd-106">\begin{align} R_1 (\theta) \mathrel{: =} \operatorname{diag} (1, e ^ {i\theta}).</span><span class="sxs-lookup"><span data-stu-id="ca8cd-106">\begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span></span>
<span data-ttu-id="ca8cd-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="ca8cd-107">\end{align}</span></span>

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ca8cd-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="ca8cd-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="ca8cd-109">théta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ca8cd-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ca8cd-110">Úhel, o který se má qubit otočit</span><span class="sxs-lookup"><span data-stu-id="ca8cd-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="ca8cd-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ca8cd-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ca8cd-112">Qubit, na který se má brána použít</span><span class="sxs-lookup"><span data-stu-id="ca8cd-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ca8cd-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ca8cd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ca8cd-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ca8cd-114">Remarks</span></span>

<span data-ttu-id="ca8cd-115">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="ca8cd-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```