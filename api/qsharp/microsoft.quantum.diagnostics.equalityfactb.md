---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: d3163281772bda392fbdd61ad58543e22022a600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698096"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="e04ce-102">EqualityFactB – funkce</span><span class="sxs-lookup"><span data-stu-id="e04ce-102">EqualityFactB function</span></span>

<span data-ttu-id="e04ce-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e04ce-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e04ce-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e04ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e04ce-105">Vyhodnotí, že klasická proměnná bool má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="e04ce-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="e04ce-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e04ce-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="e04ce-107">skutečnost: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e04ce-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e04ce-108">Proměnná, která se má zkontrolovat</span><span class="sxs-lookup"><span data-stu-id="e04ce-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="e04ce-109">očekáváno: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e04ce-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e04ce-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="e04ce-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="e04ce-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e04ce-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e04ce-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="e04ce-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e04ce-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e04ce-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

