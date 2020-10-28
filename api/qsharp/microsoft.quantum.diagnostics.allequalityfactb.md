---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 100aacccbfd5b45ac9f859cd89424b0ed4007f72
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698181"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="43d3c-102">AllEqualityFactB – funkce</span><span class="sxs-lookup"><span data-stu-id="43d3c-102">AllEqualityFactB function</span></span>

<span data-ttu-id="43d3c-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="43d3c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="43d3c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="43d3c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="43d3c-105">Vyhodnotí, že dvě pole logických hodnot jsou shodná.</span><span class="sxs-lookup"><span data-stu-id="43d3c-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="43d3c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="43d3c-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="43d3c-107">skutečnost: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="43d3c-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="43d3c-108">Pole, které je vytvořeno testovacím případem zájmu.</span><span class="sxs-lookup"><span data-stu-id="43d3c-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="43d3c-109">očekáváno: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="43d3c-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="43d3c-110">Pole, které je očekáváno z testovacího případu, který je předmětem zájmu.</span><span class="sxs-lookup"><span data-stu-id="43d3c-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="43d3c-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="43d3c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="43d3c-112">Zpráva, která má být vytištěna v případě, že pole nejsou shodná.</span><span class="sxs-lookup"><span data-stu-id="43d3c-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="43d3c-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="43d3c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

