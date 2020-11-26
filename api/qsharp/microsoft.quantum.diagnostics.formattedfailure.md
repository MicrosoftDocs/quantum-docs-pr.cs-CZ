---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: da809c04059d4fd0f0ec92412a3094f5b582fd91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201695"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="77e79-102">FormattedFailure – funkce</span><span class="sxs-lookup"><span data-stu-id="77e79-102">FormattedFailure function</span></span>

<span data-ttu-id="77e79-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="77e79-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="77e79-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="77e79-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="77e79-105">Vnitřní funkce používaná k selhání s smysluplnými chybovými zprávami.</span><span class="sxs-lookup"><span data-stu-id="77e79-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="77e79-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="77e79-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="77e79-107">skutečnost: t</span><span class="sxs-lookup"><span data-stu-id="77e79-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="77e79-108">očekáváno: t</span><span class="sxs-lookup"><span data-stu-id="77e79-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="77e79-109">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="77e79-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="77e79-110">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77e79-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="77e79-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="77e79-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="77e79-112">'S</span><span class="sxs-lookup"><span data-stu-id="77e79-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="77e79-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="77e79-113">Remarks</span></span>

<span data-ttu-id="77e79-114">Tato funkce má být emulovaná modulem runtime simulace, aby bylo možné předávat naformátované odpory.</span><span class="sxs-lookup"><span data-stu-id="77e79-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>