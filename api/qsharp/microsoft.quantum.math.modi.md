---
uid: Microsoft.Quantum.Math.ModI
title: ModI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModI
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: e0d735096ce00b97ac42b336ac226e8e25879c94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195014"
---
# <a name="modi-function"></a><span data-ttu-id="a604d-102">ModI – funkce</span><span class="sxs-lookup"><span data-stu-id="a604d-102">ModI function</span></span>

<span data-ttu-id="a604d-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a604d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a604d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a604d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a604d-105">Vrátí zbytek čísla s ohledem na jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="a604d-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="a604d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a604d-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a604d-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a604d-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a604d-108">Vstupní $a $, jejichž zbytek má být vrácen.</span><span class="sxs-lookup"><span data-stu-id="a604d-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--int"></a><span data-ttu-id="a604d-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a604d-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a604d-110">Číslo s ohledem na to, jaké zbytky $a $ mají být vráceny.</span><span class="sxs-lookup"><span data-stu-id="a604d-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="a604d-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a604d-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a604d-112">Zbytky $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="a604d-112">The modulus $a \bmod b$.</span></span>