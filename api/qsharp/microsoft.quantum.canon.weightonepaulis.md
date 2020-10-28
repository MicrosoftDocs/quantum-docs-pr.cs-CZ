---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 89802c1bc6f3da8edef27b698eb61098e47dfc85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698788"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="a45ee-102">WeightOnePaulis – funkce</span><span class="sxs-lookup"><span data-stu-id="a45ee-102">WeightOnePaulis function</span></span>

<span data-ttu-id="a45ee-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a45ee-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a45ee-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a45ee-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a45ee-105">Vrátí pole všech Paulich operátorů Weight-1 na daném počtu qubits.</span><span class="sxs-lookup"><span data-stu-id="a45ee-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="a45ee-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a45ee-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="a45ee-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a45ee-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a45ee-108">Počet qubits, na kterých jsou definovány vracené operátory Pauli</span><span class="sxs-lookup"><span data-stu-id="a45ee-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="a45ee-109">Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="a45ee-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="a45ee-110">Pole qubitch Paulich operátorů, z nichž každý je reprezentován jako pole s délkou `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="a45ee-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>