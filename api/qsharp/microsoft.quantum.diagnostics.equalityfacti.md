---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 27c0642f6d89aaa715526092813240e11b9ab530
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201831"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="4d2ac-102">EqualityFactI – funkce</span><span class="sxs-lookup"><span data-stu-id="4d2ac-102">EqualityFactI function</span></span>

<span data-ttu-id="4d2ac-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4d2ac-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4d2ac-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d2ac-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d2ac-105">Vyhodnotí, že proměnná klasického int má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="4d2ac-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="4d2ac-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4d2ac-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="4d2ac-107">skutečnost: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d2ac-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4d2ac-108">Číslo, které má být zkontrolováno.</span><span class="sxs-lookup"><span data-stu-id="4d2ac-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="4d2ac-109">očekáváno: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d2ac-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4d2ac-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="4d2ac-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="4d2ac-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4d2ac-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="4d2ac-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="4d2ac-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4d2ac-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4d2ac-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

