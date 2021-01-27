---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: Operace InjectPi4YRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 249c347c9e9729e719eda69e4e9a21847d9a46eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825947"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="f24ff-102">Operace InjectPi4YRotation</span><span class="sxs-lookup"><span data-stu-id="f24ff-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="f24ff-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f24ff-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f24ff-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f24ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f24ff-105">Otočí jeden qubit o π/4 o ose Y.</span><span class="sxs-lookup"><span data-stu-id="f24ff-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="f24ff-106">Popis</span><span class="sxs-lookup"><span data-stu-id="f24ff-106">Description</span></span>

<span data-ttu-id="f24ff-107">Provede rotaci π/4 o `Y` .</span><span class="sxs-lookup"><span data-stu-id="f24ff-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="f24ff-108">Rotace se provádí spotřebou Magic State; To znamená, že kopie stavu $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} .</span><span class="sxs-lookup"><span data-stu-id="f24ff-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="f24ff-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f24ff-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="f24ff-110">Vstup</span><span class="sxs-lookup"><span data-stu-id="f24ff-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="f24ff-111">data: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f24ff-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f24ff-112">Qubit, který se má otočit o $Y $ by $ \pi/$4.</span><span class="sxs-lookup"><span data-stu-id="f24ff-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="f24ff-113">Magic: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f24ff-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f24ff-114">Qubit je zpočátku ve stavu Magic.</span><span class="sxs-lookup"><span data-stu-id="f24ff-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="f24ff-115">Po provedení této operace `magic` se vrátí do stavu $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="f24ff-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f24ff-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f24ff-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f24ff-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f24ff-117">Remarks</span></span>

<span data-ttu-id="f24ff-118">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="f24ff-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="f24ff-119">a</span><span class="sxs-lookup"><span data-stu-id="f24ff-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="f24ff-120">Tato operace podporuje `Adjoint` funktor. v takovém případě se používá stejný stav Magic, ale vlivem na data qubit je rotace $-\ PI/4 $ $Y $-.</span><span class="sxs-lookup"><span data-stu-id="f24ff-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>