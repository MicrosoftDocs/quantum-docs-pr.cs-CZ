---
uid: Microsoft.Quantum.Math.ModL
title: ModL – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 0b1ac69cc1474e9cfa6a3489b2b2fdf497e812e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227790"
---
# <a name="modl-function"></a><span data-ttu-id="e07af-102">ModL – funkce</span><span class="sxs-lookup"><span data-stu-id="e07af-102">ModL function</span></span>

<span data-ttu-id="e07af-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e07af-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e07af-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e07af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e07af-105">Vrátí zbytek čísla s ohledem na jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="e07af-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="e07af-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e07af-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="e07af-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e07af-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e07af-108">Vstupní $a $, jejichž zbytek má být vrácen.</span><span class="sxs-lookup"><span data-stu-id="e07af-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="e07af-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e07af-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e07af-110">Číslo s ohledem na to, jaké zbytky $a $ mají být vráceny.</span><span class="sxs-lookup"><span data-stu-id="e07af-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="e07af-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e07af-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e07af-112">Zbytky $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="e07af-112">The modulus $a \bmod b$.</span></span>