---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698180"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="49de1-102">AllEqualityFactI – funkce</span><span class="sxs-lookup"><span data-stu-id="49de1-102">AllEqualityFactI function</span></span>

<span data-ttu-id="49de1-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="49de1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="49de1-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="49de1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="49de1-105">Vyhodnotí, že dvě pole celočíselných hodnot jsou shodná.</span><span class="sxs-lookup"><span data-stu-id="49de1-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="49de1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="49de1-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="49de1-107">skutečnost: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="49de1-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="49de1-108">Pole, které je vytvořeno testovacím případem zájmu.</span><span class="sxs-lookup"><span data-stu-id="49de1-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="49de1-109">očekáváno: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="49de1-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="49de1-110">Pole, které je očekáváno z testovacího případu, který je předmětem zájmu.</span><span class="sxs-lookup"><span data-stu-id="49de1-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="49de1-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="49de1-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="49de1-112">Zpráva, která má být vytištěna v případě, že pole nejsou shodná.</span><span class="sxs-lookup"><span data-stu-id="49de1-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="49de1-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49de1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

