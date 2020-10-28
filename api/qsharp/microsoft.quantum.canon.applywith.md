---
uid: Microsoft.Quantum.Canon.ApplyWith
title: Operace ApplyWith
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWith
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 61047ea2ea249e5a4d39b5747c542462c9632138
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704616"
---
# <a name="applywith-operation"></a><span data-ttu-id="e24ff-102">Operace ApplyWith</span><span class="sxs-lookup"><span data-stu-id="e24ff-102">ApplyWith operation</span></span>

<span data-ttu-id="e24ff-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e24ff-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e24ff-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e24ff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e24ff-105">Dané dvě operace platí pro sebe jako sdružené s druhou.</span><span class="sxs-lookup"><span data-stu-id="e24ff-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWith<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="e24ff-106">Popis</span><span class="sxs-lookup"><span data-stu-id="e24ff-106">Description</span></span>

<span data-ttu-id="e24ff-107">Vzhledem k dvěma operacím, které jsou popsány v rámci $U $ a $V $, jsou použity v sekvenci $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="e24ff-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="e24ff-108">To znamená, že tato operace implementuje jednotkový operátor, který je dán $V $ sdružený s $U $.</span><span class="sxs-lookup"><span data-stu-id="e24ff-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="e24ff-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="e24ff-109">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="e24ff-110">outerOperation: t [=> ADJ](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e24ff-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="e24ff-111">Operace $U $, která se má použít pro sdruženou $V $</span><span class="sxs-lookup"><span data-stu-id="e24ff-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="e24ff-112">Všimněte si, že vnější operace $U $ musí být sousední, ale nemusí být ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="e24ff-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit"></a><span data-ttu-id="e24ff-113">innerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e24ff-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e24ff-114">Operace $V $ je sdružená.</span><span class="sxs-lookup"><span data-stu-id="e24ff-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="e24ff-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="e24ff-115">target : 'T</span></span>

<span data-ttu-id="e24ff-116">Vstup, který má být poskytnut vnější a vnitřní operaci.</span><span class="sxs-lookup"><span data-stu-id="e24ff-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e24ff-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e24ff-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e24ff-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e24ff-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e24ff-119">'S</span><span class="sxs-lookup"><span data-stu-id="e24ff-119">'T</span></span>

<span data-ttu-id="e24ff-120">Cíl, na kterém každá z vnitřních a vnějších operací působí.</span><span class="sxs-lookup"><span data-stu-id="e24ff-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="e24ff-121">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e24ff-121">Remarks</span></span>

<span data-ttu-id="e24ff-122">Vnější operace se vždycky předpokládá jako sousední, ale nemusí být ovladatelné, aby se kombinovaná operace dala řídit.</span><span class="sxs-lookup"><span data-stu-id="e24ff-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="e24ff-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="e24ff-123">See Also</span></span>

- [<span data-ttu-id="e24ff-124">Microsoft. proApplyWithA. Canon.</span><span class="sxs-lookup"><span data-stu-id="e24ff-124">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="e24ff-125">Microsoft. proApplyWithC. Canon.</span><span class="sxs-lookup"><span data-stu-id="e24ff-125">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [<span data-ttu-id="e24ff-126">Microsoft. proApplyWithCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="e24ff-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)