---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: Operace ApplyCurriedOpC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: 65e861914b57cf8a32f2321f881248830b72c54e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841915"
---
# <a name="applycurriedopc-operation"></a><span data-ttu-id="527d0-102">Operace ApplyCurriedOpC</span><span class="sxs-lookup"><span data-stu-id="527d0-102">ApplyCurriedOpC operation</span></span>

<span data-ttu-id="527d0-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="527d0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="527d0-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="527d0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="527d0-105">Vstup</span><span class="sxs-lookup"><span data-stu-id="527d0-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="527d0-106">curriedOp: t-> ' U => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="527d0-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="527d0-107">First: t</span><span class="sxs-lookup"><span data-stu-id="527d0-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="527d0-108">sekundy: U</span><span class="sxs-lookup"><span data-stu-id="527d0-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="527d0-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="527d0-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="527d0-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="527d0-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="527d0-111">'S</span><span class="sxs-lookup"><span data-stu-id="527d0-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="527d0-112">U</span><span class="sxs-lookup"><span data-stu-id="527d0-112">'U</span></span>

