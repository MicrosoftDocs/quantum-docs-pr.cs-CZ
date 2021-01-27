---
uid: Microsoft.Quantum.Canon.NoOp
title: Operace NoOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 45f3c8c9d4bae8ac8f7f60c4e4f8ead5d92e7c00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852396"
---
# <a name="noop-operation"></a><span data-ttu-id="c7cb8-102">Operace NoOp</span><span class="sxs-lookup"><span data-stu-id="c7cb8-102">NoOp operation</span></span>

<span data-ttu-id="c7cb8-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c7cb8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c7cb8-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c7cb8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c7cb8-105">Provede v argumentu operaci identity (No-OP).</span><span class="sxs-lookup"><span data-stu-id="c7cb8-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c7cb8-106">Popis</span><span class="sxs-lookup"><span data-stu-id="c7cb8-106">Description</span></span>

<span data-ttu-id="c7cb8-107">Tato operace přebírá hodnotu libovolného typu a nedělá k ní nic.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="c7cb8-108">To může být užitečné, kdykoli je očekáván vstup typu operace, ale není nutné provádět žádnou akci.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="c7cb8-109">Například pokud konkrétní oprava chyby Syndrome značí, že nedošlo k žádné chybě, `NoOp<Qubit[]>` může se jednat o správný postup obnovení.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="c7cb8-110">Podobně pokud operace očekává jako vstup proceduru přípravy stavu, dá se `NoOp<Qubit[]>` použít k přípravě stavu $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="c7cb8-111">Vstup</span><span class="sxs-lookup"><span data-stu-id="c7cb8-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="c7cb8-112">vstup: t</span><span class="sxs-lookup"><span data-stu-id="c7cb8-112">input : 'T</span></span>

<span data-ttu-id="c7cb8-113">Hodnota, která má být ignorována.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c7cb8-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7cb8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c7cb8-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c7cb8-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c7cb8-116">'S</span><span class="sxs-lookup"><span data-stu-id="c7cb8-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="c7cb8-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c7cb8-117">Remarks</span></span>

<span data-ttu-id="c7cb8-118">Ve většině případů je parametr typu pro `NoOp` nutné zadat explicitně.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="c7cb8-119">Například `NoOp<Qubit>` je stejný jako <xref:microsoft.quantum.intrinsic.i> .</span><span class="sxs-lookup"><span data-stu-id="c7cb8-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7cb8-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="c7cb8-120">See Also</span></span>

- [<span data-ttu-id="c7cb8-121">Microsoft. stavová. vnitřní. I</span><span class="sxs-lookup"><span data-stu-id="c7cb8-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)