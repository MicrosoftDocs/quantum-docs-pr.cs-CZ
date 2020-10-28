---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: Operace GreaterThan
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: b7214b43dacd07b4750be4b681f30937185ac953
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707288"
---
# <a name="greaterthan-operation"></a><span data-ttu-id="b4155-102">Operace GreaterThan</span><span class="sxs-lookup"><span data-stu-id="b4155-102">GreaterThan operation</span></span>

<span data-ttu-id="b4155-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b4155-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b4155-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b4155-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b4155-105">Aplikuje větší porovnání dvou celých čísel zakódovaných do registrů qubit a Překlopí cílovou qubit na základě výsledku porovnání.</span><span class="sxs-lookup"><span data-stu-id="b4155-105">Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.</span></span>

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="b4155-106">Popis</span><span class="sxs-lookup"><span data-stu-id="b4155-106">Description</span></span>

<span data-ttu-id="b4155-107">Provede striktně větší než porovnání dvou celých čísel $x $ a $y $ kódovaný v qubit Registry XS a y.</span><span class="sxs-lookup"><span data-stu-id="b4155-107">Carries out a strictly greater than comparison of two integers $x$ and $y$, encoded in qubit registers xs and ys.</span></span> <span data-ttu-id="b4155-108">Pokud $x > y $, qubit výsledku se překlopí, jinak se výsledek qubit.</span><span class="sxs-lookup"><span data-stu-id="b4155-108">If $x > y$, then the result qubit will be flipped, otherwise the result qubit will retain its state.</span></span>

## <a name="input"></a><span data-ttu-id="b4155-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="b4155-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="b4155-110">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b4155-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b4155-111">LittleEndian qubit registruje kódování prvního celého čísla $x $.</span><span class="sxs-lookup"><span data-stu-id="b4155-111">LittleEndian qubit register encoding the first integer $x$.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="b4155-112">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b4155-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b4155-113">LittleEndian qubit registruje kódování druhého celého čísla $y $.</span><span class="sxs-lookup"><span data-stu-id="b4155-113">LittleEndian qubit register encoding the second integer $y$.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="b4155-114">výsledek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b4155-114">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b4155-115">Jeden qubit, který se překlopí, pokud $x > a $.</span><span class="sxs-lookup"><span data-stu-id="b4155-115">Single qubit that will be flipped if $x > y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b4155-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4155-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b4155-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b4155-117">Remarks</span></span>

<span data-ttu-id="b4155-118">Používá štych, který $x-y = (x ' + y) ' $, kde ', kde ' označuje první doplněk.</span><span class="sxs-lookup"><span data-stu-id="b4155-118">Uses the trick that $x - y = (x'+y)'$, where ' denotes the one's complement.</span></span>

## <a name="references"></a><span data-ttu-id="b4155-119">Odkazy</span><span class="sxs-lookup"><span data-stu-id="b4155-119">References</span></span>

- <span data-ttu-id="b4155-120">Steven A. Cuccaro, Tomáš G. Draper, Samuel A. Kutin, David Petrie Moulton: "nové v rámci Ripple – přenést okruh", 2004.</span><span class="sxs-lookup"><span data-stu-id="b4155-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1

- <span data-ttu-id="b4155-121">Tomáš Haener, Martin Roetteler, Krysta M. Svore: "faktoring pomocí 2n + 2 qubits s modulární násobení Toffoli", 2016 https://arxiv.org/abs/1611.07995</span><span class="sxs-lookup"><span data-stu-id="b4155-121">Thomas Haener, Martin Roetteler, Krysta M. Svore: "Factoring using 2n+2 qubits with Toffoli based modular multiplication", 2016 https://arxiv.org/abs/1611.07995</span></span>