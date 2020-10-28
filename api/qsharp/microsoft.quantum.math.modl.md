---
uid: Microsoft.Quantum.Math.ModL
title: ModL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 15b11a59d189aa881da9fb514cf0fe3bc9f20201
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708266"
---
# <a name="modl-function"></a><span data-ttu-id="cccd4-102">ModL – funkce</span><span class="sxs-lookup"><span data-stu-id="cccd4-102">ModL function</span></span>

<span data-ttu-id="cccd4-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="cccd4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="cccd4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cccd4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cccd4-105">Vrátí zbytek čísla s ohledem na jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="cccd4-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="cccd4-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cccd4-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="cccd4-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cccd4-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cccd4-108">Vstupní $a $, jejichž zbytek má být vrácen.</span><span class="sxs-lookup"><span data-stu-id="cccd4-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="cccd4-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cccd4-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cccd4-110">Číslo s ohledem na to, jaké zbytky $a $ mají být vráceny.</span><span class="sxs-lookup"><span data-stu-id="cccd4-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="cccd4-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cccd4-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cccd4-112">Zbytky $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="cccd4-112">The modulus $a \bmod b$.</span></span>