---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 414b703151b9152aa69709d9c28e68e5ae63506f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228861"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="55066-102">WithZeroInsertedAt – funkce</span><span class="sxs-lookup"><span data-stu-id="55066-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="55066-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="55066-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="55066-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55066-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55066-105">Vložení 0 bitové čárky do celého čísla</span><span class="sxs-lookup"><span data-stu-id="55066-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="55066-106">Popis</span><span class="sxs-lookup"><span data-stu-id="55066-106">Description</span></span>

<span data-ttu-id="55066-107">Tato operace přebírá celé číslo, vloží hodnotu 0 v bitu `position` a vrátí aktualizovanou hodnotu jako celé číslo.</span><span class="sxs-lookup"><span data-stu-id="55066-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="55066-108">Například vložení 0 na pozici 2 v numberu 10 (100 USD _ {10} = 1010_ {2} $) vrátí číslo 18 ($18 _ {10} = 10010_ {2} $).</span><span class="sxs-lookup"><span data-stu-id="55066-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="55066-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="55066-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="55066-110">pozice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55066-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55066-111">Pozice, na kterou je vložen 0</span><span class="sxs-lookup"><span data-stu-id="55066-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="55066-112">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55066-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55066-113">Hodnota, která je změněna</span><span class="sxs-lookup"><span data-stu-id="55066-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="55066-114">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55066-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55066-115">Upravená hodnota</span><span class="sxs-lookup"><span data-stu-id="55066-115">Modified value</span></span>