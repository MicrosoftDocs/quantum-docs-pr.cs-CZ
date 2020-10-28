---
uid: Microsoft.Quantum.Math.ModI
title: ModI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModI
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: d5581c5e2e4f0bcb4f8eec78464292e23031155c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708271"
---
# <a name="modi-function"></a><span data-ttu-id="8a483-102">ModI – funkce</span><span class="sxs-lookup"><span data-stu-id="8a483-102">ModI function</span></span>

<span data-ttu-id="8a483-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="8a483-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="8a483-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8a483-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8a483-105">Vrátí zbytek čísla s ohledem na jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="8a483-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="8a483-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8a483-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="8a483-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8a483-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8a483-108">Vstupní $a $, jejichž zbytek má být vrácen.</span><span class="sxs-lookup"><span data-stu-id="8a483-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--int"></a><span data-ttu-id="8a483-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8a483-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8a483-110">Číslo s ohledem na to, jaké zbytky $a $ mají být vráceny.</span><span class="sxs-lookup"><span data-stu-id="8a483-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="8a483-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8a483-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8a483-112">Zbytky $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="8a483-112">The modulus $a \bmod b$.</span></span>