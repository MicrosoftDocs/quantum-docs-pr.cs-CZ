---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704497"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="727bd-102">ArrangedQubits – funkce</span><span class="sxs-lookup"><span data-stu-id="727bd-102">ArrangedQubits function</span></span>

<span data-ttu-id="727bd-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="727bd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="727bd-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="727bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="727bd-105">Uspořádání ovládacího prvku, cíle a pomocníka qubits podle indexu</span><span class="sxs-lookup"><span data-stu-id="727bd-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="727bd-106">Popis</span><span class="sxs-lookup"><span data-stu-id="727bd-106">Description</span></span>

<span data-ttu-id="727bd-107">Vrátí pole qubit s cílem v indexu 0 a ovládací prvek i na indexu 2 ^ i.</span><span class="sxs-lookup"><span data-stu-id="727bd-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="727bd-108">Pomocná qubits se vloží do všech ostatních pozic v poli.</span><span class="sxs-lookup"><span data-stu-id="727bd-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="727bd-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="727bd-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="727bd-110">ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="727bd-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="727bd-111">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="727bd-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="727bd-112">pomocný objekt: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="727bd-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="727bd-113">Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="727bd-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

