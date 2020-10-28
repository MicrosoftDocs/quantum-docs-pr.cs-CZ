---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708374"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="df1a8-102">IsCoprimeI – funkce</span><span class="sxs-lookup"><span data-stu-id="df1a8-102">IsCoprimeI function</span></span>

<span data-ttu-id="df1a8-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="df1a8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="df1a8-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="df1a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="df1a8-105">Vrátí hodnotu true, pokud $a $ a $b $ jsou souběžné a false v opačném případě.</span><span class="sxs-lookup"><span data-stu-id="df1a8-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="df1a8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="df1a8-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="df1a8-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df1a8-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df1a8-108">první počet primality, které se testují společně</span><span class="sxs-lookup"><span data-stu-id="df1a8-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="df1a8-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df1a8-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df1a8-110">druhý počet, který provádí testování primality</span><span class="sxs-lookup"><span data-stu-id="df1a8-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="df1a8-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="df1a8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="df1a8-112">True, pokud $a $ a $b $ jsou souběžné (například jejich největší společný dělitel je 1) a jinak false</span><span class="sxs-lookup"><span data-stu-id="df1a8-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>