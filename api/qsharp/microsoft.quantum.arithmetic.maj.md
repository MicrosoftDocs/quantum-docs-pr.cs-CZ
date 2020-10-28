---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: Operace MAJ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: c1801d1d7ed04ead11b672f24d44a94989cf8f1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707208"
---
# <a name="maj-operation"></a><span data-ttu-id="47e11-102">Operace MAJ</span><span class="sxs-lookup"><span data-stu-id="47e11-102">MAJ operation</span></span>

<span data-ttu-id="47e11-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="47e11-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="47e11-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47e11-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47e11-105">To aplikuje operaci na místní většinu na 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="47e11-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="47e11-106">Popis</span><span class="sxs-lookup"><span data-stu-id="47e11-106">Description</span></span>

<span data-ttu-id="47e11-107">Pokud budeme poznamenat stav cílové qubit jako $ \ket{z} $ a vstupní stavy vstupních qubits jako $ \ket{x} $ a $ \ket{y} $, pak tato operace provede následující transformaci: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{maj} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="47e11-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="47e11-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="47e11-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="47e11-109">input0: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="47e11-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="47e11-110">První vstupní qubit</span><span class="sxs-lookup"><span data-stu-id="47e11-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="47e11-111">input1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="47e11-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="47e11-112">Druhý vstup qubit.</span><span class="sxs-lookup"><span data-stu-id="47e11-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="47e11-113">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="47e11-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="47e11-114">Qubit, na který se použije většina funkce.</span><span class="sxs-lookup"><span data-stu-id="47e11-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="47e11-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47e11-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

