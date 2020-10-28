---
uid: Microsoft.Quantum.Canon.ConjugatedBy
title: ConjugatedBy – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedBy
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 37fbee9a7c11991645933a372f9f12c1fd696b66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704344"
---
# <a name="conjugatedby-function"></a><span data-ttu-id="e404c-102">ConjugatedBy – funkce</span><span class="sxs-lookup"><span data-stu-id="e404c-102">ConjugatedBy function</span></span>

<span data-ttu-id="e404c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e404c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e404c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e404c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e404c-105">Pro dané vnější a vnitřní operace vrátí novou operaci, která přijedná vnitřní operaci do sdružené operace vnější operací.</span><span class="sxs-lookup"><span data-stu-id="e404c-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedBy<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit)) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="e404c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e404c-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="e404c-107">outerOperation: t [=> ADJ](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e404c-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="e404c-108">Operace $U $, která se má použít pro sdruženou $V $</span><span class="sxs-lookup"><span data-stu-id="e404c-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="e404c-109">Všimněte si, že vnější operace $U $ musí být sousední, ale nemusí být ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="e404c-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit"></a><span data-ttu-id="e404c-110">innerOperation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e404c-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e404c-111">Operace $V $ je sdružená.</span><span class="sxs-lookup"><span data-stu-id="e404c-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="e404c-112">Výstup: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e404c-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e404c-113">Nová operace, jejíž akce je reprezentovaná jednotkou $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="e404c-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e404c-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e404c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e404c-115">'S</span><span class="sxs-lookup"><span data-stu-id="e404c-115">'T</span></span>

<span data-ttu-id="e404c-116">Typ cíle, na kterém každá z vnitřních a vnějších operací působí.</span><span class="sxs-lookup"><span data-stu-id="e404c-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="e404c-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e404c-117">Remarks</span></span>

<span data-ttu-id="e404c-118">Vnější operace se vždycky předpokládá jako sousední, ale nemusí být ovladatelné, aby se kombinovaná operace dala řídit.</span><span class="sxs-lookup"><span data-stu-id="e404c-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="e404c-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="e404c-119">See Also</span></span>

- [<span data-ttu-id="e404c-120">Microsoft. proConjugatedByA. Canon.</span><span class="sxs-lookup"><span data-stu-id="e404c-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="e404c-121">Microsoft. proConjugatedByC. Canon.</span><span class="sxs-lookup"><span data-stu-id="e404c-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="e404c-122">Microsoft. proConjugatedByCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="e404c-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="e404c-123">Microsoft. proApplyWith. Canon.</span><span class="sxs-lookup"><span data-stu-id="e404c-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)