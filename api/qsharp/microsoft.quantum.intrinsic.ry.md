---
uid: Microsoft.Quantum.Intrinsic.Ry
title: Operace ry
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 9966693eb7283e855f7b72e910aa3604d6c2bd61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706536"
---
# <a name="ry-operation"></a><span data-ttu-id="2e1db-102">Operace ry</span><span class="sxs-lookup"><span data-stu-id="2e1db-102">Ry operation</span></span>

<span data-ttu-id="2e1db-103">Obor názvů: [Microsoft.. vnitřní](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2e1db-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2e1db-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2e1db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2e1db-105">Aplikuje otočení o $y ose $ na daném úhlu.</span><span class="sxs-lookup"><span data-stu-id="2e1db-105">Applies a rotation about the $y$-axis by a given angle.</span></span>

<span data-ttu-id="2e1db-106">\begin{align} R_y (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_y/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-\sin \frac{\theta} {2} \\ \\ \sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="2e1db-106">\begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="2e1db-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2e1db-107">\end{align}</span></span>

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="2e1db-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="2e1db-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="2e1db-109">théta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2e1db-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2e1db-110">Úhel, o který se má qubit otočit</span><span class="sxs-lookup"><span data-stu-id="2e1db-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="2e1db-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2e1db-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2e1db-112">Qubit, na který se má brána použít</span><span class="sxs-lookup"><span data-stu-id="2e1db-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e1db-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e1db-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2e1db-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2e1db-114">Remarks</span></span>

<span data-ttu-id="2e1db-115">Ekvivalent:</span><span class="sxs-lookup"><span data-stu-id="2e1db-115">Equivalent to:</span></span>

```qsharp
R(PauliY, theta, qubit);
```