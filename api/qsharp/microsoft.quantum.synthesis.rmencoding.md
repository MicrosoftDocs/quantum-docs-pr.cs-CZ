---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: f3c54d2e40511dacb21618b4eaf1eef9f4903f9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855330"
---
# <a name="rmencoding-function"></a><span data-ttu-id="e347a-102">RMEncoding – funkce</span><span class="sxs-lookup"><span data-stu-id="e347a-102">RMEncoding function</span></span>

<span data-ttu-id="e347a-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="e347a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="e347a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e347a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e347a-105">{-1,1} kódování logické hodnoty pravdy</span><span class="sxs-lookup"><span data-stu-id="e347a-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="e347a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e347a-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="e347a-107">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e347a-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e347a-108">Logická hodnota</span><span class="sxs-lookup"><span data-stu-id="e347a-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="e347a-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e347a-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e347a-110">1, pokud `b` je false, v opačném případě-1</span><span class="sxs-lookup"><span data-stu-id="e347a-110">1, if `b` is false, otherwise -1</span></span>