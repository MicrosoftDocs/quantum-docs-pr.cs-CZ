---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 6efc9da5f5ebb64065a90e749daa629dc2dce9cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708494"
---
# <a name="inversemodi-function"></a><span data-ttu-id="db6e8-102">InverseModI – funkce</span><span class="sxs-lookup"><span data-stu-id="db6e8-102">InverseModI function</span></span>

<span data-ttu-id="db6e8-103">Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="db6e8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="db6e8-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="db6e8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="db6e8-105">Vrátí $b $ tak, že $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="db6e8-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="db6e8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="db6e8-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="db6e8-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db6e8-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db6e8-108">Počet, který se obrátí</span><span class="sxs-lookup"><span data-stu-id="db6e8-108">The number being inverted</span></span>


### <a name="modulus--int"></a><span data-ttu-id="db6e8-109">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db6e8-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db6e8-110">Zbytek v závislosti na tom, které hodnoty jsou obráceny</span><span class="sxs-lookup"><span data-stu-id="db6e8-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--int"></a><span data-ttu-id="db6e8-111">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db6e8-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db6e8-112">Integer $b $, což $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="db6e8-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>