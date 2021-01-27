---
uid: Microsoft.Quantum.Math.ModL
title: ModL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: f044ae16d93d31d0f28f5fcf076cff2bfef62eb8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846845"
---
# <a name="modl-function"></a><span data-ttu-id="42d0a-102">ModL – funkce</span><span class="sxs-lookup"><span data-stu-id="42d0a-102">ModL function</span></span>

<span data-ttu-id="42d0a-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="42d0a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="42d0a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42d0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42d0a-105">Vrátí zbytek čísla s ohledem na jiné číslo.</span><span class="sxs-lookup"><span data-stu-id="42d0a-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="42d0a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="42d0a-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="42d0a-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="42d0a-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="42d0a-108">Vstupní $a $, jejichž zbytek má být vrácen.</span><span class="sxs-lookup"><span data-stu-id="42d0a-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="42d0a-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="42d0a-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="42d0a-110">Číslo s ohledem na to, jaké zbytky $a $ mají být vráceny.</span><span class="sxs-lookup"><span data-stu-id="42d0a-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="42d0a-111">Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="42d0a-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="42d0a-112">Zbytky $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="42d0a-112">The modulus $a \bmod b$.</span></span>