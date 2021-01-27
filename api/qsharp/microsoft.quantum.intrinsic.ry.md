---
uid: Microsoft.Quantum.Intrinsic.Ry
title: Operace ry
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: b50225b67701c6b17475445d5ed54400240e0b69
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818284"
---
# <a name="ry-operation"></a><span data-ttu-id="97ea0-102">Operace ry</span><span class="sxs-lookup"><span data-stu-id="97ea0-102">Ry operation</span></span>

<span data-ttu-id="97ea0-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="97ea0-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="97ea0-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="97ea0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="97ea0-105">Aplikuje otočení o $y ose $ na daném úhlu.</span><span class="sxs-lookup"><span data-stu-id="97ea0-105">Applies a rotation about the $y$-axis by a given angle.</span></span>

<span data-ttu-id="97ea0-106">\begin{align} R_y (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_y/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-\sin \frac{\theta} {2} \\ \\ \sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="97ea0-106">\begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="97ea0-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="97ea0-107">\end{align}</span></span>

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="97ea0-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="97ea0-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="97ea0-109">théta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="97ea0-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="97ea0-110">Úhel, o který se má qubit otočit</span><span class="sxs-lookup"><span data-stu-id="97ea0-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="97ea0-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="97ea0-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="97ea0-112">Qubit, na který se má brána použít</span><span class="sxs-lookup"><span data-stu-id="97ea0-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="97ea0-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="97ea0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="97ea0-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="97ea0-114">Remarks</span></span>

<span data-ttu-id="97ea0-115">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="97ea0-115">Equivalent to:</span></span>

```qsharp
R(PauliY, theta, qubit);
```