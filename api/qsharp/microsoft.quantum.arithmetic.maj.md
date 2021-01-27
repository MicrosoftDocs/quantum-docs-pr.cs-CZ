---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: Operace MAJ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 68236f1deeb409a01152d4b7e854202a1134314e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846553"
---
# <a name="maj-operation"></a><span data-ttu-id="9b53f-102">Operace MAJ</span><span class="sxs-lookup"><span data-stu-id="9b53f-102">MAJ operation</span></span>

<span data-ttu-id="9b53f-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9b53f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9b53f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b53f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b53f-105">To aplikuje operaci na místní většinu na 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="9b53f-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9b53f-106">Popis</span><span class="sxs-lookup"><span data-stu-id="9b53f-106">Description</span></span>

<span data-ttu-id="9b53f-107">Pokud budeme poznamenat stav cílové qubit jako $ \ket{z} $ a vstupní stavy vstupních qubits jako $ \ket{x} $ a $ \ket{y} $, pak tato operace provede následující transformaci: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{maj} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="9b53f-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="9b53f-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="9b53f-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="9b53f-109">input0: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9b53f-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9b53f-110">První vstupní qubit</span><span class="sxs-lookup"><span data-stu-id="9b53f-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="9b53f-111">input1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9b53f-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9b53f-112">Druhý vstup qubit.</span><span class="sxs-lookup"><span data-stu-id="9b53f-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9b53f-113">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9b53f-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9b53f-114">Qubit, na který se použije většina funkce.</span><span class="sxs-lookup"><span data-stu-id="9b53f-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b53f-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b53f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

