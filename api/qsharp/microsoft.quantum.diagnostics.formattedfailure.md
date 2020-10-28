---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698068"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="e1b2e-102">FormattedFailure – funkce</span><span class="sxs-lookup"><span data-stu-id="e1b2e-102">FormattedFailure function</span></span>

<span data-ttu-id="e1b2e-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e1b2e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e1b2e-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1b2e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1b2e-105">Vnitřní funkce používaná k selhání s smysluplnými chybovými zprávami.</span><span class="sxs-lookup"><span data-stu-id="e1b2e-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="e1b2e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e1b2e-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="e1b2e-107">skutečnost: t</span><span class="sxs-lookup"><span data-stu-id="e1b2e-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="e1b2e-108">očekáváno: t</span><span class="sxs-lookup"><span data-stu-id="e1b2e-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="e1b2e-109">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e1b2e-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="e1b2e-110">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1b2e-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e1b2e-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e1b2e-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e1b2e-112">'S</span><span class="sxs-lookup"><span data-stu-id="e1b2e-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="e1b2e-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e1b2e-113">Remarks</span></span>

<span data-ttu-id="e1b2e-114">Tato funkce má být emulovaná modulem runtime simulace, aby bylo možné předávat naformátované odpory.</span><span class="sxs-lookup"><span data-stu-id="e1b2e-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>