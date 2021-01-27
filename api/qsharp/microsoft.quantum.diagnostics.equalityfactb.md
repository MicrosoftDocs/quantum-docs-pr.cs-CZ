---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: cb1d4c471c528d2d3c08c92619fafd532a88c8f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829206"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="5b7f1-102">EqualityFactB – funkce</span><span class="sxs-lookup"><span data-stu-id="5b7f1-102">EqualityFactB function</span></span>

<span data-ttu-id="5b7f1-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5b7f1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5b7f1-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5b7f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5b7f1-105">Vyhodnotí, že klasická proměnná bool má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="5b7f1-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="5b7f1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5b7f1-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="5b7f1-107">skutečnost: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5b7f1-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5b7f1-108">Proměnná, která se má zkontrolovat</span><span class="sxs-lookup"><span data-stu-id="5b7f1-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="5b7f1-109">očekáváno: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5b7f1-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5b7f1-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="5b7f1-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="5b7f1-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="5b7f1-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="5b7f1-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="5b7f1-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5b7f1-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5b7f1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

