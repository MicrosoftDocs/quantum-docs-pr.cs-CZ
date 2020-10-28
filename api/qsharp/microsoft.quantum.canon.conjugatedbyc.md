---
uid: Microsoft.Quantum.Canon.ConjugatedByC
title: ConjugatedByC – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByC
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: c4c381e40c5a941487bcf78ebe5339574aedb45d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704336"
---
# <a name="conjugatedbyc-function"></a><span data-ttu-id="8b837-102">ConjugatedByC – funkce</span><span class="sxs-lookup"><span data-stu-id="8b837-102">ConjugatedByC function</span></span>

<span data-ttu-id="8b837-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8b837-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8b837-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b837-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8b837-105">Pro dané vnější a vnitřní operace vrátí novou operaci, která přijedná vnitřní operaci do sdružené operace vnější operací.</span><span class="sxs-lookup"><span data-stu-id="8b837-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl)) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="8b837-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8b837-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="8b837-107">outerOperation: t [=> ADJ](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b837-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="8b837-108">Operace $U $, která se má použít pro sdruženou $V $</span><span class="sxs-lookup"><span data-stu-id="8b837-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="8b837-109">Všimněte si, že vnější operace $U $ musí být sousední, ale nemusí být ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="8b837-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-ctl"></a><span data-ttu-id="8b837-110">innerOperation: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="8b837-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="8b837-111">Operace $V $ je sdružená.</span><span class="sxs-lookup"><span data-stu-id="8b837-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="8b837-112">Výstup: t => seznam CTL pro [jednotku](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b837-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="8b837-113">Nová operace, jejíž akce je reprezentovaná jednotkou $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="8b837-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8b837-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8b837-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8b837-115">'S</span><span class="sxs-lookup"><span data-stu-id="8b837-115">'T</span></span>

<span data-ttu-id="8b837-116">Typ cíle, na kterém každá z vnitřních a vnějších operací působí.</span><span class="sxs-lookup"><span data-stu-id="8b837-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b837-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="8b837-117">Remarks</span></span>

<span data-ttu-id="8b837-118">Vnější operace se vždycky předpokládá jako sousední, ale nemusí být ovladatelné, aby se kombinovaná operace dala řídit.</span><span class="sxs-lookup"><span data-stu-id="8b837-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b837-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="8b837-119">See Also</span></span>

- [<span data-ttu-id="8b837-120">Microsoft. proConjugatedBy. Canon.</span><span class="sxs-lookup"><span data-stu-id="8b837-120">Microsoft.Quantum.Canon.ConjugatedBy</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedBy)
- [<span data-ttu-id="8b837-121">Microsoft. proConjugatedByA. Canon.</span><span class="sxs-lookup"><span data-stu-id="8b837-121">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="8b837-122">Microsoft. proConjugatedByCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="8b837-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="8b837-123">Microsoft. proApplyWith. Canon.</span><span class="sxs-lookup"><span data-stu-id="8b837-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)