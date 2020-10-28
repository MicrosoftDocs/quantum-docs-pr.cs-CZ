---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704352"
---
# <a name="composedoutput-function"></a><span data-ttu-id="62da9-102">ComposedOutput – funkce</span><span class="sxs-lookup"><span data-stu-id="62da9-102">ComposedOutput function</span></span>

<span data-ttu-id="62da9-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="62da9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="62da9-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="62da9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="62da9-105">Vrátí výstup složení `inner` a `outer` pro daný vstup.</span><span class="sxs-lookup"><span data-stu-id="62da9-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="62da9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="62da9-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="62da9-107">vnější: U-> V</span><span class="sxs-lookup"><span data-stu-id="62da9-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="62da9-108">vnitřní: t-> ' U</span><span class="sxs-lookup"><span data-stu-id="62da9-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="62da9-109">cíl: t</span><span class="sxs-lookup"><span data-stu-id="62da9-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="62da9-110">Výstup: ' V</span><span class="sxs-lookup"><span data-stu-id="62da9-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="62da9-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="62da9-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="62da9-112">'S</span><span class="sxs-lookup"><span data-stu-id="62da9-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="62da9-113">U</span><span class="sxs-lookup"><span data-stu-id="62da9-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="62da9-114">V</span><span class="sxs-lookup"><span data-stu-id="62da9-114">'V</span></span>

