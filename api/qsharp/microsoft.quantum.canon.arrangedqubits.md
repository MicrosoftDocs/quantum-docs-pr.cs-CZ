---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 07a4ed5fe99dedb333246f7161d157dcd01a01da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841080"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="3d434-102">ArrangedQubits – funkce</span><span class="sxs-lookup"><span data-stu-id="3d434-102">ArrangedQubits function</span></span>

<span data-ttu-id="3d434-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3d434-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3d434-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3d434-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3d434-105">Uspořádání ovládacího prvku, cíle a pomocníka qubits podle indexu</span><span class="sxs-lookup"><span data-stu-id="3d434-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="3d434-106">Popis</span><span class="sxs-lookup"><span data-stu-id="3d434-106">Description</span></span>

<span data-ttu-id="3d434-107">Vrátí pole qubit s cílem v indexu 0 a ovládací prvek i na indexu 2 ^ i.</span><span class="sxs-lookup"><span data-stu-id="3d434-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="3d434-108">Pomocná qubits se vloží do všech ostatních pozic v poli.</span><span class="sxs-lookup"><span data-stu-id="3d434-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="3d434-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="3d434-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="3d434-110">ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3d434-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="3d434-111">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3d434-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="3d434-112">pomocný objekt: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3d434-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="3d434-113">Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3d434-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

