---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: Operace ApplyCurriedOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: ab652159fa64a95401d07998ed4aaae5c4dbb92e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219018"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="22234-102">Operace ApplyCurriedOp</span><span class="sxs-lookup"><span data-stu-id="22234-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="22234-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="22234-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="22234-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22234-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="22234-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="22234-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="22234-106">curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="22234-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="22234-107">First: t</span><span class="sxs-lookup"><span data-stu-id="22234-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="22234-108">sekundy: U</span><span class="sxs-lookup"><span data-stu-id="22234-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="22234-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="22234-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="22234-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="22234-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="22234-111">'S</span><span class="sxs-lookup"><span data-stu-id="22234-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="22234-112">U</span><span class="sxs-lookup"><span data-stu-id="22234-112">'U</span></span>

