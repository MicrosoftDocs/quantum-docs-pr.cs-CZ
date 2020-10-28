---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Operace CompareUsingRippleCarry
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: 842e7ded1e38f4f6e01e79d2758e30afb85dd349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707377"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="41573-102">Operace CompareUsingRippleCarry</span><span class="sxs-lookup"><span data-stu-id="41573-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="41573-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="41573-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="41573-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="41573-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="41573-105">Tato operace testuje, zda celé číslo reprezentované registrem qubits je větší než jiné celé číslo, a použití funkce XOR výsledku na výstupní qubit.</span><span class="sxs-lookup"><span data-stu-id="41573-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="41573-106">Popis</span><span class="sxs-lookup"><span data-stu-id="41573-106">Description</span></span>

<span data-ttu-id="41573-107">Zadaná dvě celá čísla `x` a `y` uložená v qubit registrech se stejnou velikostí, tato operace kontroluje, jestli splňují `x > y` .</span><span class="sxs-lookup"><span data-stu-id="41573-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="41573-108">Pokud je nastaveno na true, je 1 XORed do výstupního qubit.</span><span class="sxs-lookup"><span data-stu-id="41573-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="41573-109">V opačném případě je 0 XORed do výstupního qubit.</span><span class="sxs-lookup"><span data-stu-id="41573-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="41573-110">Jinými slovy Tato operace může být reprezentována jednotkou $ $ \begin{align} U\ket {x} \ KET {y} \ KET {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span><span class="sxs-lookup"><span data-stu-id="41573-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="41573-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="41573-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="41573-112">Vstup</span><span class="sxs-lookup"><span data-stu-id="41573-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="41573-113">x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="41573-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="41573-114">První číslo, které má být porovnáno, uloženo ve `LittleEndian` formátu v qubit registru.</span><span class="sxs-lookup"><span data-stu-id="41573-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="41573-115">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="41573-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="41573-116">Druhé číslo, které má být porovnáno, uloženo ve `LittleEndian` formátu v qubit registru.</span><span class="sxs-lookup"><span data-stu-id="41573-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="41573-117">výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="41573-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="41573-118">Qubit, který ukládá výsledek porovnání $x>a $.</span><span class="sxs-lookup"><span data-stu-id="41573-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="41573-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="41573-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="41573-120">Odkazy</span><span class="sxs-lookup"><span data-stu-id="41573-120">References</span></span>

- <span data-ttu-id="41573-121">Nové v rámci Ripple – přenést okruh Steven A. Cuccaro, Tomáš G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="41573-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>