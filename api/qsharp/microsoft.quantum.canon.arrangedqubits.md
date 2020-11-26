---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f3bc4dff73d5ad6393294fc3770b8d36e6094fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217063"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="52ce6-102">ArrangedQubits – funkce</span><span class="sxs-lookup"><span data-stu-id="52ce6-102">ArrangedQubits function</span></span>

<span data-ttu-id="52ce6-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="52ce6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="52ce6-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52ce6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52ce6-105">Uspořádání ovládacího prvku, cíle a pomocníka qubits podle indexu</span><span class="sxs-lookup"><span data-stu-id="52ce6-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="52ce6-106">Popis</span><span class="sxs-lookup"><span data-stu-id="52ce6-106">Description</span></span>

<span data-ttu-id="52ce6-107">Vrátí pole qubit s cílem v indexu 0 a ovládací prvek i na indexu 2 ^ i.</span><span class="sxs-lookup"><span data-stu-id="52ce6-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="52ce6-108">Pomocná qubits se vloží do všech ostatních pozic v poli.</span><span class="sxs-lookup"><span data-stu-id="52ce6-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="52ce6-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="52ce6-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="52ce6-110">ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="52ce6-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="52ce6-111">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="52ce6-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="52ce6-112">pomocný objekt: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="52ce6-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="52ce6-113">Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="52ce6-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

