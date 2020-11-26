---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 3b3ac3f9f8b70307099de60899c969abb2acad7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197666"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="aefcb-102">LessThanLexographic – funkce</span><span class="sxs-lookup"><span data-stu-id="aefcb-102">LessThanLexographic function</span></span>

<span data-ttu-id="aefcb-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="aefcb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="aefcb-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aefcb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aefcb-105">Používá se k implementaci `LexographicComparison` .</span><span class="sxs-lookup"><span data-stu-id="aefcb-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="aefcb-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="aefcb-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="aefcb-107">porovnání: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="aefcb-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="aefcb-108">Left: t []</span><span class="sxs-lookup"><span data-stu-id="aefcb-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="aefcb-109">Right: t []</span><span class="sxs-lookup"><span data-stu-id="aefcb-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="aefcb-110">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="aefcb-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="aefcb-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="aefcb-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aefcb-112">'S</span><span class="sxs-lookup"><span data-stu-id="aefcb-112">'T</span></span>

