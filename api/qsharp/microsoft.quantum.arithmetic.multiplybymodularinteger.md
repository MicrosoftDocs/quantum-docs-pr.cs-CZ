---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Operace MultiplyByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706392"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="52433-102">Operace MultiplyByModularInteger</span><span class="sxs-lookup"><span data-stu-id="52433-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="52433-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="52433-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="52433-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="52433-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="52433-105">Provede modulární násobení pomocí celočíselné konstanty v qubit registru.</span><span class="sxs-lookup"><span data-stu-id="52433-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="52433-106">Popis</span><span class="sxs-lookup"><span data-stu-id="52433-106">Description</span></span>

<span data-ttu-id="52433-107">Poznamenejte si je `modulus` $N $ a `constMultiplier` pomocí $a $.</span><span class="sxs-lookup"><span data-stu-id="52433-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="52433-108">Tato operace pak implementuje jednotnou operaci definovanou na základě následujícího mapování na výpočetní bázi: $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ pro všechny $y $ mezi $0 $ a $N-$1.</span><span class="sxs-lookup"><span data-stu-id="52433-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="52433-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="52433-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="52433-110">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="52433-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="52433-111">Konstanta, o kterou se násobí násobitel.</span><span class="sxs-lookup"><span data-stu-id="52433-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="52433-112">Musí být souběžně s modulem.</span><span class="sxs-lookup"><span data-stu-id="52433-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="52433-113">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="52433-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="52433-114">Operace násobení je prováděna modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="52433-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="52433-115">násobitel: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="52433-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="52433-116">Číslo vynásobené konstantou.</span><span class="sxs-lookup"><span data-stu-id="52433-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="52433-117">Toto je pole qubits kódování celé číslo ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="52433-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="52433-118">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52433-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="52433-119">Poznámky</span><span class="sxs-lookup"><span data-stu-id="52433-119">Remarks</span></span>

- <span data-ttu-id="52433-120">Pro diagram okruhu a vysvětlení viz obrázek 7 na [stránce 8 arXiv: quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="52433-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="52433-121">Tato operace odpovídá ₐ U v [arXiv: quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="52433-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>