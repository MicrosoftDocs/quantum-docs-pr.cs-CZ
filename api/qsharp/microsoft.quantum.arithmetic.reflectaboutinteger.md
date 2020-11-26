---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: Operace ReflectAboutInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: d4bae0cba5ee45e8d48070e36efab0159ade9137
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222367"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="794d4-102">Operace ReflectAboutInteger</span><span class="sxs-lookup"><span data-stu-id="794d4-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="794d4-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="794d4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="794d4-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="794d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="794d4-105">Odráží pokladnu v registru o daném klasickém čísle.</span><span class="sxs-lookup"><span data-stu-id="794d4-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="794d4-106">Popis</span><span class="sxs-lookup"><span data-stu-id="794d4-106">Description</span></span>

<span data-ttu-id="794d4-107">Vzhledem k prvnímu zaregistrování do stavu $ \ sum_i \ alpha_i \ket{i} $, kde každý $ \ket{i} $ je základní stav reprezentující celé číslo $i $, odráží stav registru pro základní stav pro dané celé číslo $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {IJ}} \ alpha_i \ket{i} $ $</span><span class="sxs-lookup"><span data-stu-id="794d4-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="794d4-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="794d4-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="794d4-109">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="794d4-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="794d4-110">Klasické celé číslo, které indexuje základní stav, o který se má odrážet.</span><span class="sxs-lookup"><span data-stu-id="794d4-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="794d4-111">REG: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="794d4-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="794d4-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="794d4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="794d4-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="794d4-113">Remarks</span></span>

<span data-ttu-id="794d4-114">Tato operace je implementována místně bez explicitního přidělení dalších pomocných qubits.</span><span class="sxs-lookup"><span data-stu-id="794d4-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>