---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Odporující funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: f9ad9a7d67bda8e50c76f679f535ad55ba07698e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202137"
---
# <a name="contradiction-function"></a><span data-ttu-id="bd6a6-102">Odporující funkce</span><span class="sxs-lookup"><span data-stu-id="bd6a6-102">Contradiction function</span></span>

<span data-ttu-id="bd6a6-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="bd6a6-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="bd6a6-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bd6a6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bd6a6-105">Deklaruje, že klasická podmínka je nepravdivá.</span><span class="sxs-lookup"><span data-stu-id="bd6a6-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="bd6a6-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="bd6a6-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="bd6a6-107">skutečnost: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bd6a6-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bd6a6-108">Podmínka, která má být deklarována.</span><span class="sxs-lookup"><span data-stu-id="bd6a6-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="bd6a6-109">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bd6a6-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="bd6a6-110">Řetězec zprávy o selhání, který se má vytisknout v případě, že je klasická podmínka pravdivá</span><span class="sxs-lookup"><span data-stu-id="bd6a6-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bd6a6-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd6a6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="bd6a6-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="bd6a6-112">See Also</span></span>

- [<span data-ttu-id="bd6a6-113">Microsoft. provedl. Diagnostics. fakt</span><span class="sxs-lookup"><span data-stu-id="bd6a6-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)