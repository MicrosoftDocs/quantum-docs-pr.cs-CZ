---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Odporující funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698121"
---
# <a name="contradiction-function"></a><span data-ttu-id="ad7ce-102">Odporující funkce</span><span class="sxs-lookup"><span data-stu-id="ad7ce-102">Contradiction function</span></span>

<span data-ttu-id="ad7ce-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ad7ce-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ad7ce-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ad7ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ad7ce-105">Deklaruje, že klasická podmínka je nepravdivá.</span><span class="sxs-lookup"><span data-stu-id="ad7ce-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="ad7ce-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ad7ce-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="ad7ce-107">skutečnost: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ad7ce-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ad7ce-108">Podmínka, která má být deklarována.</span><span class="sxs-lookup"><span data-stu-id="ad7ce-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="ad7ce-109">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ad7ce-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ad7ce-110">Řetězec zprávy o selhání, který se má vytisknout v případě, že je klasická podmínka pravdivá</span><span class="sxs-lookup"><span data-stu-id="ad7ce-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ad7ce-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad7ce-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ad7ce-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="ad7ce-112">See Also</span></span>

- [<span data-ttu-id="ad7ce-113">Microsoft. provedl. Diagnostics. fakt</span><span class="sxs-lookup"><span data-stu-id="ad7ce-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)