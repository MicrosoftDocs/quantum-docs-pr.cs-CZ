---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828281"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="13c5d-102">FormattedFailure – funkce</span><span class="sxs-lookup"><span data-stu-id="13c5d-102">FormattedFailure function</span></span>

<span data-ttu-id="13c5d-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="13c5d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="13c5d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13c5d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13c5d-105">Vnitřní funkce používaná k selhání s smysluplnými chybovými zprávami.</span><span class="sxs-lookup"><span data-stu-id="13c5d-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="13c5d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="13c5d-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="13c5d-107">skutečnost: t</span><span class="sxs-lookup"><span data-stu-id="13c5d-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="13c5d-108">očekáváno: t</span><span class="sxs-lookup"><span data-stu-id="13c5d-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="13c5d-109">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="13c5d-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="13c5d-110">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="13c5d-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="13c5d-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="13c5d-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="13c5d-112">'S</span><span class="sxs-lookup"><span data-stu-id="13c5d-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="13c5d-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="13c5d-113">Remarks</span></span>

<span data-ttu-id="13c5d-114">Tato funkce má být emulovaná modulem runtime simulace, aby bylo možné předávat naformátované odpory.</span><span class="sxs-lookup"><span data-stu-id="13c5d-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>