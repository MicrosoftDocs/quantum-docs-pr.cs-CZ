---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 360088e31a47a7bb114bc0527edf600cd78740f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697292"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="f197f-102">LessThanLexographic – funkce</span><span class="sxs-lookup"><span data-stu-id="f197f-102">LessThanLexographic function</span></span>

<span data-ttu-id="f197f-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f197f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f197f-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f197f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f197f-105">Používá se k implementaci `LexographicComparison` .</span><span class="sxs-lookup"><span data-stu-id="f197f-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="f197f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f197f-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="f197f-107">porovnání: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f197f-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="f197f-108">Left: t []</span><span class="sxs-lookup"><span data-stu-id="f197f-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="f197f-109">Right: t []</span><span class="sxs-lookup"><span data-stu-id="f197f-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="f197f-110">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f197f-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f197f-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f197f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f197f-112">'S</span><span class="sxs-lookup"><span data-stu-id="f197f-112">'T</span></span>

