---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpCA
title: Operace ApplyCurriedOpCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpCA
qsharp.summary: ''
ms.openlocfilehash: df534a3156ac3f5411161c6faf4d39759e49fbed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218899"
---
# <a name="applycurriedopca-operation"></a><span data-ttu-id="c3efe-102">Operace ApplyCurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="c3efe-102">ApplyCurriedOpCA operation</span></span>

<span data-ttu-id="c3efe-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c3efe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c3efe-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3efe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj)), first : 'T, second : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c3efe-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="c3efe-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj--ctl"></a><span data-ttu-id="c3efe-106">curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c3efe-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="c3efe-107">First: t</span><span class="sxs-lookup"><span data-stu-id="c3efe-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="c3efe-108">sekundy: U</span><span class="sxs-lookup"><span data-stu-id="c3efe-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="c3efe-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3efe-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c3efe-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c3efe-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c3efe-111">'S</span><span class="sxs-lookup"><span data-stu-id="c3efe-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="c3efe-112">U</span><span class="sxs-lookup"><span data-stu-id="c3efe-112">'U</span></span>

