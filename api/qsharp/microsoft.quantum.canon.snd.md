---
uid: Microsoft.Quantum.Canon.Snd
title: SND – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c935a2bc9e3f5ab32669feae2bfc0f2ebf57e744
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205316"
---
# <a name="snd-function"></a><span data-ttu-id="033d1-102">SND – funkce</span><span class="sxs-lookup"><span data-stu-id="033d1-102">Snd function</span></span>

<span data-ttu-id="033d1-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="033d1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="033d1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="033d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="033d1-105">S ohledem na pár vrátí jeho druhý prvek.</span><span class="sxs-lookup"><span data-stu-id="033d1-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="033d1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="033d1-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="033d1-107">dvojice: (t, ' U)</span><span class="sxs-lookup"><span data-stu-id="033d1-107">pair : ('T,'U)</span></span>

<span data-ttu-id="033d1-108">Řazená kolekce členů se dvěma prvky.</span><span class="sxs-lookup"><span data-stu-id="033d1-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="033d1-109">Výstup: ' U</span><span class="sxs-lookup"><span data-stu-id="033d1-109">Output : 'U</span></span>

<span data-ttu-id="033d1-110">Druhý prvek elementu `pair` .</span><span class="sxs-lookup"><span data-stu-id="033d1-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="033d1-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="033d1-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="033d1-112">'S</span><span class="sxs-lookup"><span data-stu-id="033d1-112">'T</span></span>

<span data-ttu-id="033d1-113">Typ prvního člena dvojice.</span><span class="sxs-lookup"><span data-stu-id="033d1-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="033d1-114">U</span><span class="sxs-lookup"><span data-stu-id="033d1-114">'U</span></span>

<span data-ttu-id="033d1-115">Typ druhého člena dvojice.</span><span class="sxs-lookup"><span data-stu-id="033d1-115">The type of the pair's second member.</span></span>