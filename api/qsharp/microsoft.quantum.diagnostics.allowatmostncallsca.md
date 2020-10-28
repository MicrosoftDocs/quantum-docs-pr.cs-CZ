---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Operace AllowAtMostNCallsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698177"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="ad13c-102">Operace AllowAtMostNCallsCA</span><span class="sxs-lookup"><span data-stu-id="ad13c-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="ad13c-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ad13c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ad13c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ad13c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ad13c-105">Mezi voláním této operace a jejím sousedním objektem vyhodnotí, že daná operace je volána nejvíce po určitou dobu.</span><span class="sxs-lookup"><span data-stu-id="ad13c-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="ad13c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ad13c-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="ad13c-107">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ad13c-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ad13c-108">Maximální počet pokusů, které `op` mohou být volány.</span><span class="sxs-lookup"><span data-stu-id="ad13c-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput-adj--ctl"></a><span data-ttu-id="ad13c-109">op: TInput => ' TOutput ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="ad13c-109">op : 'TInput => 'TOutput Adj + Ctl</span></span>

<span data-ttu-id="ad13c-110">Operace, jejíž volání mají být omezeny.</span><span class="sxs-lookup"><span data-stu-id="ad13c-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="ad13c-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ad13c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ad13c-112">Zpráva, která se má zobrazit při selhání</span><span class="sxs-lookup"><span data-stu-id="ad13c-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ad13c-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad13c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ad13c-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ad13c-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="ad13c-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="ad13c-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="ad13c-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="ad13c-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="ad13c-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ad13c-117">Remarks</span></span>

<span data-ttu-id="ad13c-118">Tato operace může být nahrazena operací no-op u cílů, které ji nepodporují.</span><span class="sxs-lookup"><span data-stu-id="ad13c-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>