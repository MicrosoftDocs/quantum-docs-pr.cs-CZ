---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 53131a755571ad1ac0a8a984bf229b16f67dbe51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195354"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="88aeb-102">IsCoprimeI – funkce</span><span class="sxs-lookup"><span data-stu-id="88aeb-102">IsCoprimeI function</span></span>

<span data-ttu-id="88aeb-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="88aeb-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="88aeb-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88aeb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88aeb-105">Vrátí hodnotu true, pokud $a $ a $b $ jsou souběžné a false v opačném případě.</span><span class="sxs-lookup"><span data-stu-id="88aeb-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="88aeb-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="88aeb-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="88aeb-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="88aeb-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="88aeb-108">první počet primality, které se testují společně</span><span class="sxs-lookup"><span data-stu-id="88aeb-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="88aeb-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="88aeb-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="88aeb-110">druhý počet, který provádí testování primality</span><span class="sxs-lookup"><span data-stu-id="88aeb-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="88aeb-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="88aeb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="88aeb-112">True, pokud $a $ a $b $ jsou souběžné (například jejich největší společný dělitel je 1) a jinak false</span><span class="sxs-lookup"><span data-stu-id="88aeb-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>