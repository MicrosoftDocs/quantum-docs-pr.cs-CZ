---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Operace MultiplyByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: bd4e0ad6c5bad779d9a31139690021fd9fcda210
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846490"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="ffb49-102">Operace MultiplyByModularInteger</span><span class="sxs-lookup"><span data-stu-id="ffb49-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="ffb49-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ffb49-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ffb49-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ffb49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ffb49-105">Provede modulární násobení pomocí celočíselné konstanty v qubit registru.</span><span class="sxs-lookup"><span data-stu-id="ffb49-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ffb49-106">Popis</span><span class="sxs-lookup"><span data-stu-id="ffb49-106">Description</span></span>

<span data-ttu-id="ffb49-107">Poznamenejte si je `modulus` $N $ a `constMultiplier` pomocí $a $.</span><span class="sxs-lookup"><span data-stu-id="ffb49-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="ffb49-108">Tato operace pak implementuje jednotnou operaci definovanou na základě následujícího mapování na výpočetní bázi: $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ pro všechny $y $ mezi $0 $ a $N-$1.</span><span class="sxs-lookup"><span data-stu-id="ffb49-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="ffb49-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="ffb49-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="ffb49-110">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ffb49-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ffb49-111">Konstanta, o kterou se násobí násobitel.</span><span class="sxs-lookup"><span data-stu-id="ffb49-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="ffb49-112">Musí být souběžně s modulem.</span><span class="sxs-lookup"><span data-stu-id="ffb49-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="ffb49-113">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ffb49-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ffb49-114">Operace násobení je prováděna modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="ffb49-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="ffb49-115">násobitel: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ffb49-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ffb49-116">Číslo vynásobené konstantou.</span><span class="sxs-lookup"><span data-stu-id="ffb49-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="ffb49-117">Toto je pole qubits kódování celé číslo ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="ffb49-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ffb49-118">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ffb49-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ffb49-119">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ffb49-119">Remarks</span></span>

- <span data-ttu-id="ffb49-120">Pro diagram okruhu a vysvětlení viz obrázek 7 na [stránce 8 arXiv: quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="ffb49-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="ffb49-121">Tato operace odpovídá ₐ U v [arXiv: quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="ffb49-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>