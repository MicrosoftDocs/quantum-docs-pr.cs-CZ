---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 7c077d508c93672d58a52a1403b3c5d73df75471
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707924"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="4b1d0-102">IsCoprimeL – funkce</span><span class="sxs-lookup"><span data-stu-id="4b1d0-102">IsCoprimeL function</span></span>

<span data-ttu-id="4b1d0-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4b1d0-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4b1d0-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b1d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b1d0-105">Vrátí hodnotu true, pokud $a $ a $b $ jsou souběžné a false v opačném případě.</span><span class="sxs-lookup"><span data-stu-id="4b1d0-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="4b1d0-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4b1d0-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4b1d0-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4b1d0-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4b1d0-108">první počet primality, které se testují společně</span><span class="sxs-lookup"><span data-stu-id="4b1d0-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="4b1d0-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4b1d0-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4b1d0-110">druhý počet, který provádí testování primality</span><span class="sxs-lookup"><span data-stu-id="4b1d0-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="4b1d0-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4b1d0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4b1d0-112">True, pokud $a $ a $b $ jsou souběžné (například jejich největší společný dělitel je 1) a jinak false</span><span class="sxs-lookup"><span data-stu-id="4b1d0-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>