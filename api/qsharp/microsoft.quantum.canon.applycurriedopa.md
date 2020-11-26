---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: Operace ApplyCurriedOpA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: db3f63cbe2ee5ef048c7e378864d68696f55331f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218950"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="a7922-102">Operace ApplyCurriedOpA</span><span class="sxs-lookup"><span data-stu-id="a7922-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="a7922-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a7922-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a7922-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7922-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="a7922-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="a7922-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="a7922-106">curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="a7922-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="a7922-107">First: t</span><span class="sxs-lookup"><span data-stu-id="a7922-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="a7922-108">sekundy: U</span><span class="sxs-lookup"><span data-stu-id="a7922-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="a7922-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7922-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a7922-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a7922-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a7922-111">'S</span><span class="sxs-lookup"><span data-stu-id="a7922-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="a7922-112">U</span><span class="sxs-lookup"><span data-stu-id="a7922-112">'U</span></span>

