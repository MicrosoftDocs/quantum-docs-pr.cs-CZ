---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Operace ApplyMajorityInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 3664ffe96cd1db8cf5e8898387fe7f2d45b4ea98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707593"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="b8517-102">Operace ApplyMajorityInPlace</span><span class="sxs-lookup"><span data-stu-id="b8517-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="b8517-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b8517-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b8517-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b8517-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b8517-105">Aplikuje operaci se třemi qubity na místě v registru qubits.</span><span class="sxs-lookup"><span data-stu-id="b8517-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="b8517-106">Popis</span><span class="sxs-lookup"><span data-stu-id="b8517-106">Description</span></span>

<span data-ttu-id="b8517-107">Tato operace vypočítá funkci většina místa na 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="b8517-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="b8517-108">Pokud si vyhledáme výstup qubit jako $z $ a vstupní qubits jako $x $ a $y $, operace provede následující transformaci: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{maj} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="b8517-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="b8517-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="b8517-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="b8517-110">výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b8517-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b8517-111">První vstupní qubit</span><span class="sxs-lookup"><span data-stu-id="b8517-111">First input qubit.</span></span> <span data-ttu-id="b8517-112">Všimněte si, že výstup je vypočítán místně a je uložený v tomto qubit.</span><span class="sxs-lookup"><span data-stu-id="b8517-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="b8517-113">vstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b8517-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b8517-114">Druhé a třetí vstupní qubits.</span><span class="sxs-lookup"><span data-stu-id="b8517-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b8517-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b8517-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

