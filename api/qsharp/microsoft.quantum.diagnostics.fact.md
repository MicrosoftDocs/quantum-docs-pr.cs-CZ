---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fakt – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853306"
---
# <a name="fact-function"></a><span data-ttu-id="7c317-102">Fakt – funkce</span><span class="sxs-lookup"><span data-stu-id="7c317-102">Fact function</span></span>

<span data-ttu-id="7c317-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7c317-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7c317-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7c317-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7c317-105">Deklaruje, že klasická podmínka je pravdivá.</span><span class="sxs-lookup"><span data-stu-id="7c317-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="7c317-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7c317-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="7c317-107">skutečnost: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7c317-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7c317-108">Podmínka, která má být deklarována.</span><span class="sxs-lookup"><span data-stu-id="7c317-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="7c317-109">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7c317-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="7c317-110">Řetězec zprávy o selhání, který se má vytisknout v případě, že je klasická podmínka nepravdivá</span><span class="sxs-lookup"><span data-stu-id="7c317-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c317-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c317-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="7c317-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="7c317-112">Example</span></span>

<span data-ttu-id="7c317-113">Následující fragment kódu Q # se nezdaří:</span><span class="sxs-lookup"><span data-stu-id="7c317-113">The following Q# snippet will fail:</span></span>

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a><span data-ttu-id="7c317-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="7c317-114">See Also</span></span>

- [<span data-ttu-id="7c317-115">Microsoft. prověří. Diagnostics. rozpor</span><span class="sxs-lookup"><span data-stu-id="7c317-115">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)