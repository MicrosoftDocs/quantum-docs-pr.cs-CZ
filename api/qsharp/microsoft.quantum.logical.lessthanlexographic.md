---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 716f58b747e9f58c338670271bb2e7aed96fe98c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815645"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="797b5-102">LessThanLexographic – funkce</span><span class="sxs-lookup"><span data-stu-id="797b5-102">LessThanLexographic function</span></span>

<span data-ttu-id="797b5-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="797b5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="797b5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="797b5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="797b5-105">Používá se k implementaci `LexographicComparison` .</span><span class="sxs-lookup"><span data-stu-id="797b5-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="797b5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="797b5-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="797b5-107">porovnání: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="797b5-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="797b5-108">Left: t []</span><span class="sxs-lookup"><span data-stu-id="797b5-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="797b5-109">Right: t []</span><span class="sxs-lookup"><span data-stu-id="797b5-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="797b5-110">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="797b5-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="797b5-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="797b5-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="797b5-112">'S</span><span class="sxs-lookup"><span data-stu-id="797b5-112">'T</span></span>

