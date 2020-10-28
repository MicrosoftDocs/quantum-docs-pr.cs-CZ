---
uid: Microsoft.Quantum.Intrinsic.Rx
title: Operace RX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 6d11c8fa3c3fb2c07a88fdf2cba0ff2a7f51bf6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708439"
---
# <a name="rx-operation"></a><span data-ttu-id="e4b56-102">Operace RX</span><span class="sxs-lookup"><span data-stu-id="e4b56-102">Rx operation</span></span>

<span data-ttu-id="e4b56-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="e4b56-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="e4b56-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4b56-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4b56-105">Aplikuje otočení o $x ose $ na daném úhlu.</span><span class="sxs-lookup"><span data-stu-id="e4b56-105">Applies a rotation about the $x$-axis by a given angle.</span></span>

<span data-ttu-id="e4b56-106">\begin{align} R_x (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_x/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-i\sin \frac{\theta} {2} \\ \\ -i\sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="e4b56-106">\begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="e4b56-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e4b56-107">\end{align}</span></span>

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e4b56-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="e4b56-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="e4b56-109">théta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e4b56-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e4b56-110">Úhel, o který se má qubit otočit</span><span class="sxs-lookup"><span data-stu-id="e4b56-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="e4b56-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e4b56-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e4b56-112">Qubit, na který se má brána použít</span><span class="sxs-lookup"><span data-stu-id="e4b56-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e4b56-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e4b56-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e4b56-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e4b56-114">Remarks</span></span>

<span data-ttu-id="e4b56-115">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="e4b56-115">Equivalent to:</span></span>

```qsharp
R(PauliX, theta, qubit);
```