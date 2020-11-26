---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223880"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="9b890-102">AllEqualityFactI – funkce</span><span class="sxs-lookup"><span data-stu-id="9b890-102">AllEqualityFactI function</span></span>

<span data-ttu-id="9b890-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9b890-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9b890-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b890-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b890-105">Vyhodnotí, že dvě pole celočíselných hodnot jsou shodná.</span><span class="sxs-lookup"><span data-stu-id="9b890-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="9b890-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="9b890-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="9b890-107">skutečnost: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9b890-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9b890-108">Pole, které je vytvořeno testovacím případem zájmu.</span><span class="sxs-lookup"><span data-stu-id="9b890-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="9b890-109">očekáváno: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9b890-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9b890-110">Pole, které je očekáváno z testovacího případu, který je předmětem zájmu.</span><span class="sxs-lookup"><span data-stu-id="9b890-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="9b890-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9b890-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9b890-112">Zpráva, která má být vytištěna v případě, že pole nejsou shodná.</span><span class="sxs-lookup"><span data-stu-id="9b890-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b890-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b890-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

