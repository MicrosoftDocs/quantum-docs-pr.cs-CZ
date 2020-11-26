---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: Operace ApplyWithCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: e86c452e9693c5a4d0d4e5a36471ab46bbf66dfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208138"
---
# <a name="applywithca-operation"></a><span data-ttu-id="6d80c-102">Operace ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="6d80c-102">ApplyWithCA operation</span></span>

<span data-ttu-id="6d80c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6d80c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6d80c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6d80c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6d80c-105">Dané dvě operace platí pro sebe jako sdružené s druhou.</span><span class="sxs-lookup"><span data-stu-id="6d80c-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6d80c-106">Popis</span><span class="sxs-lookup"><span data-stu-id="6d80c-106">Description</span></span>

<span data-ttu-id="6d80c-107">Vzhledem k dvěma operacím, které jsou popsány v rámci $U $ a $V $, jsou použity v sekvenci $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="6d80c-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="6d80c-108">To znamená, že tato operace implementuje jednotkový operátor, který je dán $V $ sdružený s $U $.</span><span class="sxs-lookup"><span data-stu-id="6d80c-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="6d80c-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="6d80c-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="6d80c-110">outerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="6d80c-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6d80c-111">Operace $U $, která se má použít pro sdruženou $V $</span><span class="sxs-lookup"><span data-stu-id="6d80c-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="6d80c-112">Všimněte si, že vnější operace $U $ musí být sousední, ale nemusí být ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="6d80c-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj--ctl"></a><span data-ttu-id="6d80c-113">innerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="6d80c-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6d80c-114">Operace $V $ je sdružená.</span><span class="sxs-lookup"><span data-stu-id="6d80c-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="6d80c-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="6d80c-115">target : 'T</span></span>

<span data-ttu-id="6d80c-116">Vstup, který má být poskytnut vnější a vnitřní operaci.</span><span class="sxs-lookup"><span data-stu-id="6d80c-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6d80c-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6d80c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6d80c-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6d80c-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6d80c-119">'S</span><span class="sxs-lookup"><span data-stu-id="6d80c-119">'T</span></span>

<span data-ttu-id="6d80c-120">Cíl, na kterém každá z vnitřních a vnějších operací působí.</span><span class="sxs-lookup"><span data-stu-id="6d80c-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="6d80c-121">Poznámky</span><span class="sxs-lookup"><span data-stu-id="6d80c-121">Remarks</span></span>

<span data-ttu-id="6d80c-122">Vnější operace se vždycky předpokládá jako sousední, ale nemusí být ovladatelné, aby se kombinovaná operace dala řídit.</span><span class="sxs-lookup"><span data-stu-id="6d80c-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d80c-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="6d80c-123">See Also</span></span>

- [<span data-ttu-id="6d80c-124">Microsoft. proApplyWith. Canon.</span><span class="sxs-lookup"><span data-stu-id="6d80c-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="6d80c-125">Microsoft. proApplyWithA. Canon.</span><span class="sxs-lookup"><span data-stu-id="6d80c-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="6d80c-126">Microsoft. proApplyWithC. Canon.</span><span class="sxs-lookup"><span data-stu-id="6d80c-126">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)