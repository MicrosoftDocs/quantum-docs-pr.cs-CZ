---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Odporující funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829367"
---
# <a name="contradiction-function"></a><span data-ttu-id="2834f-102">Odporující funkce</span><span class="sxs-lookup"><span data-stu-id="2834f-102">Contradiction function</span></span>

<span data-ttu-id="2834f-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2834f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2834f-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2834f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2834f-105">Deklaruje, že klasická podmínka je nepravdivá.</span><span class="sxs-lookup"><span data-stu-id="2834f-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2834f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2834f-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="2834f-107">skutečnost: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2834f-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2834f-108">Podmínka, která má být deklarována.</span><span class="sxs-lookup"><span data-stu-id="2834f-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="2834f-109">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2834f-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2834f-110">Řetězec zprávy o selhání, který se má vytisknout v případě, že je klasická podmínka pravdivá</span><span class="sxs-lookup"><span data-stu-id="2834f-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2834f-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2834f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="2834f-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="2834f-112">Example</span></span>

<span data-ttu-id="2834f-113">Následující kód Q # vypíše text "Hello, World":</span><span class="sxs-lookup"><span data-stu-id="2834f-113">The following Q# code will print "Hello, world":</span></span>

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a><span data-ttu-id="2834f-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="2834f-114">See Also</span></span>

- [<span data-ttu-id="2834f-115">Microsoft. provedl. Diagnostics. fakt</span><span class="sxs-lookup"><span data-stu-id="2834f-115">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)