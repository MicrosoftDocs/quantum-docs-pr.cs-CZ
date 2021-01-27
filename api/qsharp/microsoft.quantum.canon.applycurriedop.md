---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: Operace ApplyCurriedOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: c252eceb6a307ea9514aaa8aa3a3de1f9fa1b698
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841918"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="9869f-102">Operace ApplyCurriedOp</span><span class="sxs-lookup"><span data-stu-id="9869f-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="9869f-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9869f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9869f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9869f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="9869f-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="9869f-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="9869f-106">curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9869f-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="9869f-107">First: t</span><span class="sxs-lookup"><span data-stu-id="9869f-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="9869f-108">sekundy: U</span><span class="sxs-lookup"><span data-stu-id="9869f-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="9869f-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9869f-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9869f-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9869f-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9869f-111">'S</span><span class="sxs-lookup"><span data-stu-id="9869f-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="9869f-112">U</span><span class="sxs-lookup"><span data-stu-id="9869f-112">'U</span></span>

