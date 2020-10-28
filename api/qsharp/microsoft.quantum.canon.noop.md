---
uid: Microsoft.Quantum.Canon.NoOp
title: Operace NoOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 987e39577c3b736418234431ed7a915ae461f763
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698948"
---
# <a name="noop-operation"></a><span data-ttu-id="8c2e8-102">Operace NoOp</span><span class="sxs-lookup"><span data-stu-id="8c2e8-102">NoOp operation</span></span>

<span data-ttu-id="8c2e8-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8c2e8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8c2e8-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8c2e8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8c2e8-105">Provede v argumentu operaci identity (No-OP).</span><span class="sxs-lookup"><span data-stu-id="8c2e8-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="8c2e8-106">Popis</span><span class="sxs-lookup"><span data-stu-id="8c2e8-106">Description</span></span>

<span data-ttu-id="8c2e8-107">Tato operace přebírá hodnotu libovolného typu a nedělá k ní nic.</span><span class="sxs-lookup"><span data-stu-id="8c2e8-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="8c2e8-108">To může být užitečné, kdykoli je očekáván vstup typu operace, ale není nutné provádět žádnou akci.</span><span class="sxs-lookup"><span data-stu-id="8c2e8-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="8c2e8-109">Například pokud konkrétní oprava chyby Syndrome značí, že nedošlo k žádné chybě, `NoOp<Qubit[]>` může se jednat o správný postup obnovení.</span><span class="sxs-lookup"><span data-stu-id="8c2e8-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="8c2e8-110">Podobně pokud operace očekává jako vstup proceduru přípravy stavu, dá se `NoOp<Qubit[]>` použít k přípravě stavu $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="8c2e8-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="8c2e8-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="8c2e8-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="8c2e8-112">vstup: t</span><span class="sxs-lookup"><span data-stu-id="8c2e8-112">input : 'T</span></span>

<span data-ttu-id="8c2e8-113">Hodnota, která má být ignorována.</span><span class="sxs-lookup"><span data-stu-id="8c2e8-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8c2e8-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8c2e8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8c2e8-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8c2e8-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8c2e8-116">'S</span><span class="sxs-lookup"><span data-stu-id="8c2e8-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="8c2e8-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="8c2e8-117">Remarks</span></span>

<span data-ttu-id="8c2e8-118">Ve většině případů je parametr typu pro `NoOp` nutné zadat explicitně.</span><span class="sxs-lookup"><span data-stu-id="8c2e8-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="8c2e8-119">Například `NoOp<Qubit>` je stejný jako <xref:microsoft.quantum.intrinsic.i> .</span><span class="sxs-lookup"><span data-stu-id="8c2e8-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c2e8-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="8c2e8-120">See Also</span></span>

- [<span data-ttu-id="8c2e8-121">Microsoft. stavová. vnitřní. I</span><span class="sxs-lookup"><span data-stu-id="8c2e8-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)