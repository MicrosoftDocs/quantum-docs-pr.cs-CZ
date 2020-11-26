---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Operace CompareUsingRippleCarry
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: e2d6e5a663f8c4e101c7e2ab1346d10cade3f4e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223455"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="5a022-102">Operace CompareUsingRippleCarry</span><span class="sxs-lookup"><span data-stu-id="5a022-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="5a022-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5a022-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5a022-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5a022-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5a022-105">Tato operace testuje, zda celé číslo reprezentované registrem qubits je větší než jiné celé číslo, a použití funkce XOR výsledku na výstupní qubit.</span><span class="sxs-lookup"><span data-stu-id="5a022-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="5a022-106">Popis</span><span class="sxs-lookup"><span data-stu-id="5a022-106">Description</span></span>

<span data-ttu-id="5a022-107">Zadaná dvě celá čísla `x` a `y` uložená v qubit registrech se stejnou velikostí, tato operace kontroluje, jestli splňují `x > y` .</span><span class="sxs-lookup"><span data-stu-id="5a022-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="5a022-108">Pokud je nastaveno na true, je 1 XORed do výstupního qubit.</span><span class="sxs-lookup"><span data-stu-id="5a022-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="5a022-109">V opačném případě je 0 XORed do výstupního qubit.</span><span class="sxs-lookup"><span data-stu-id="5a022-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="5a022-110">Jinými slovy Tato operace může být reprezentována jednotkou $ $ \begin{align} U\ket {x} \ KET {y} \ KET {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span><span class="sxs-lookup"><span data-stu-id="5a022-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="5a022-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="5a022-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="5a022-112">Vstup</span><span class="sxs-lookup"><span data-stu-id="5a022-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="5a022-113">x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5a022-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5a022-114">První číslo, které má být porovnáno, uloženo ve `LittleEndian` formátu v qubit registru.</span><span class="sxs-lookup"><span data-stu-id="5a022-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="5a022-115">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5a022-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5a022-116">Druhé číslo, které má být porovnáno, uloženo ve `LittleEndian` formátu v qubit registru.</span><span class="sxs-lookup"><span data-stu-id="5a022-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="5a022-117">výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5a022-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5a022-118">Qubit, který ukládá výsledek porovnání $x>a $.</span><span class="sxs-lookup"><span data-stu-id="5a022-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a022-119">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a022-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="5a022-120">Reference</span><span class="sxs-lookup"><span data-stu-id="5a022-120">References</span></span>

- <span data-ttu-id="5a022-121">Nové v rámci Ripple – přenést okruh Steven A. Cuccaro, Tomáš G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="5a022-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>