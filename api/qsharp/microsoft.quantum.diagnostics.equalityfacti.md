---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: c41cb5548e8dfebb4d1c1a1c052306878c85e821
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853351"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="48129-102">EqualityFactI – funkce</span><span class="sxs-lookup"><span data-stu-id="48129-102">EqualityFactI function</span></span>

<span data-ttu-id="48129-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="48129-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="48129-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48129-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48129-105">Vyhodnotí, že proměnná klasického int má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="48129-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="48129-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="48129-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="48129-107">skutečnost: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48129-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48129-108">Číslo, které má být zkontrolováno.</span><span class="sxs-lookup"><span data-stu-id="48129-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="48129-109">očekáváno: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48129-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48129-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="48129-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="48129-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="48129-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="48129-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="48129-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="48129-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48129-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

