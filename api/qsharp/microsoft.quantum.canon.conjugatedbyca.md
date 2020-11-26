---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: ConjugatedByCA – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: acd5a9f796f751b9c9c374d841e80de9286fcd24
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207305"
---
# <a name="conjugatedbyca-function"></a><span data-ttu-id="c35bc-102">ConjugatedByCA – funkce</span><span class="sxs-lookup"><span data-stu-id="c35bc-102">ConjugatedByCA function</span></span>

<span data-ttu-id="c35bc-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c35bc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c35bc-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c35bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c35bc-105">Pro dané vnější a vnitřní operace vrátí novou operaci, která přijedná vnitřní operaci do sdružené operace vnější operací.</span><span class="sxs-lookup"><span data-stu-id="c35bc-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c35bc-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c35bc-106">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="c35bc-107">outerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="c35bc-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c35bc-108">Operace $U $, která se má použít pro sdruženou $V $</span><span class="sxs-lookup"><span data-stu-id="c35bc-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="c35bc-109">Všimněte si, že vnější operace $U $ musí být sousední, ale nemusí být ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="c35bc-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj--ctl"></a><span data-ttu-id="c35bc-110">innerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c35bc-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c35bc-111">Operace $V $ je sdružená.</span><span class="sxs-lookup"><span data-stu-id="c35bc-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="c35bc-112">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c35bc-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c35bc-113">Nová operace, jejíž akce je reprezentovaná jednotkou $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="c35bc-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c35bc-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c35bc-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c35bc-115">'S</span><span class="sxs-lookup"><span data-stu-id="c35bc-115">'T</span></span>

<span data-ttu-id="c35bc-116">Typ cíle, na kterém každá z vnitřních a vnějších operací působí.</span><span class="sxs-lookup"><span data-stu-id="c35bc-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="c35bc-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c35bc-117">Remarks</span></span>

<span data-ttu-id="c35bc-118">Vnější operace se vždycky předpokládá jako sousední, ale nemusí být ovladatelné, aby se kombinovaná operace dala řídit.</span><span class="sxs-lookup"><span data-stu-id="c35bc-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="c35bc-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="c35bc-119">See Also</span></span>

- [<span data-ttu-id="c35bc-120">Microsoft. proConjugatedByA. Canon.</span><span class="sxs-lookup"><span data-stu-id="c35bc-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="c35bc-121">Microsoft. proConjugatedByC. Canon.</span><span class="sxs-lookup"><span data-stu-id="c35bc-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="c35bc-122">Microsoft. proConjugatedByCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="c35bc-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="c35bc-123">Microsoft. proApplyWith. Canon.</span><span class="sxs-lookup"><span data-stu-id="c35bc-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)