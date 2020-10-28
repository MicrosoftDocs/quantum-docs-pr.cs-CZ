---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 34bb38a9447f71372ec0b234731f31a5818d3af1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698092"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="e7d65-102">EqualityFactI – funkce</span><span class="sxs-lookup"><span data-stu-id="e7d65-102">EqualityFactI function</span></span>

<span data-ttu-id="e7d65-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e7d65-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e7d65-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e7d65-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e7d65-105">Vyhodnotí, že proměnná klasického int má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="e7d65-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="e7d65-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e7d65-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="e7d65-107">skutečnost: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7d65-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e7d65-108">Číslo, které má být zkontrolováno.</span><span class="sxs-lookup"><span data-stu-id="e7d65-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="e7d65-109">očekáváno: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7d65-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e7d65-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="e7d65-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="e7d65-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e7d65-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e7d65-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="e7d65-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e7d65-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e7d65-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

