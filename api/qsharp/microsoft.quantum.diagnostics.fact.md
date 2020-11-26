---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fakt – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 74ec020d0437d885d7cbfc98a2c9c0c1867d5d39
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201678"
---
# <a name="fact-function"></a><span data-ttu-id="63709-102">Fakt – funkce</span><span class="sxs-lookup"><span data-stu-id="63709-102">Fact function</span></span>

<span data-ttu-id="63709-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="63709-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="63709-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="63709-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="63709-105">Deklaruje, že klasická podmínka je pravdivá.</span><span class="sxs-lookup"><span data-stu-id="63709-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="63709-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="63709-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="63709-107">skutečnost: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="63709-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="63709-108">Podmínka, která má být deklarována.</span><span class="sxs-lookup"><span data-stu-id="63709-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="63709-109">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="63709-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="63709-110">Řetězec zprávy o selhání, který se má vytisknout v případě, že je klasická podmínka nepravdivá</span><span class="sxs-lookup"><span data-stu-id="63709-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63709-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63709-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="63709-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="63709-112">See Also</span></span>

- [<span data-ttu-id="63709-113">Microsoft. prověří. Diagnostics. rozpor</span><span class="sxs-lookup"><span data-stu-id="63709-113">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)