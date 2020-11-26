---
uid: Microsoft.Quantum.Intrinsic.R1
title: Operace R1
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: a98c2cc0b309a239650afd2910cc74dffa9f899a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198805"
---
# <a name="r1-operation"></a><span data-ttu-id="63a9b-102">Operace R1</span><span class="sxs-lookup"><span data-stu-id="63a9b-102">R1 operation</span></span>

<span data-ttu-id="63a9b-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="63a9b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="63a9b-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="63a9b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="63a9b-105">Použije rotaci o stavu $ \ket {1} $ podle daného úhlu.</span><span class="sxs-lookup"><span data-stu-id="63a9b-105">Applies a rotation about the $\ket{1}$ state by a given angle.</span></span>

<span data-ttu-id="63a9b-106">\begin{align} R_1 (\theta) \mathrel{: =} \operatorname{diag} (1, e ^ {i\theta}).</span><span class="sxs-lookup"><span data-stu-id="63a9b-106">\begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span></span>
<span data-ttu-id="63a9b-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="63a9b-107">\end{align}</span></span>

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="63a9b-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="63a9b-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="63a9b-109">théta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="63a9b-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="63a9b-110">Úhel, o který se má qubit otočit</span><span class="sxs-lookup"><span data-stu-id="63a9b-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="63a9b-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="63a9b-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="63a9b-112">Qubit, na který se má brána použít</span><span class="sxs-lookup"><span data-stu-id="63a9b-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63a9b-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63a9b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="63a9b-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="63a9b-114">Remarks</span></span>

<span data-ttu-id="63a9b-115">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="63a9b-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```