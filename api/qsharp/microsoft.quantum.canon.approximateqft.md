---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Operace ApproximateQFT
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 97a410133e80cc5bffc810e9d6455baaee32364b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207696"
---
# <a name="approximateqft-operation"></a><span data-ttu-id="2c149-102">Operace ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="2c149-102">ApproximateQFT operation</span></span>

<span data-ttu-id="2c149-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2c149-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2c149-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2c149-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2c149-105">Použijte přibližnou neAQFTnou hodnotu Fourierova transformace () na registrační pokladnu.</span><span class="sxs-lookup"><span data-stu-id="2c149-105">Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.</span></span>

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2c149-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2c149-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="2c149-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2c149-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2c149-108">parametr aproximace, který určuje, na jaké úrovni se vyřadí kontrolované otočení Z okruhu QFT.</span><span class="sxs-lookup"><span data-stu-id="2c149-108">approximation parameter which determines at which level the controlled Z-rotations that occur in the QFT circuit are pruned.</span></span>

<span data-ttu-id="2c149-109">Parametr aproximace a určuje úroveň vyřazení z rotací, tj. ∈ {0.. n} a všech rotací Z 2π/2k, kde k>a jsou odebrány z okruhu QFT.</span><span class="sxs-lookup"><span data-stu-id="2c149-109">The approximation parameter a determines the pruning level of the Z-rotations, i.e., a ∈ {0..n} and all Z-rotations 2π/2ᵏ where k>a are removed from the QFT circuit.</span></span> <span data-ttu-id="2c149-110">Je známo, že pro k >= log ₂ (n) + log ₂ (1/ε) + 3 jedna se dá svázat | | QFT-AQFT | |<ε.</span><span class="sxs-lookup"><span data-stu-id="2c149-110">It is known that for k >= log₂(n)+log₂(1/ε)+3 one can bound ||QFT-AQFT||<ε.</span></span>


### <a name="qs--bigendian"></a><span data-ttu-id="2c149-111">QS: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="2c149-111">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="2c149-112">registruje se v registru n qubits, na které se použije Přibližná transformace pro Fourierova množství.</span><span class="sxs-lookup"><span data-stu-id="2c149-112">quantum register of n qubits to which the Approximate Quantum Fourier Transform is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c149-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c149-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2c149-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2c149-114">Remarks</span></span>

<span data-ttu-id="2c149-115">AQFT vyžaduje pro 2π/2k a Hadamard brány v rámci rotace.</span><span class="sxs-lookup"><span data-stu-id="2c149-115">AQFT requires Z-rotation gates of the form 2π/2ᵏ and Hadamard gates.</span></span>

<span data-ttu-id="2c149-116">Předpokládá se, že vstup a výstup se zakódují do kódování ve formátu big endian.</span><span class="sxs-lookup"><span data-stu-id="2c149-116">The input and output are assumed to be encoded in big endian encoding.</span></span>

## <a name="references"></a><span data-ttu-id="2c149-117">Reference</span><span class="sxs-lookup"><span data-stu-id="2c149-117">References</span></span>

- [<span data-ttu-id="2c149-118">*M. Roetteler, Th. Beth*, příkaz. algebraický eng. obcí. Počítal. 19 (3): 177-193 (2008)</span><span class="sxs-lookup"><span data-stu-id="2c149-118"> *M. Roetteler, Th. Beth*, Appl. Algebra Eng. Commun. Comput. 19(3): 177-193 (2008) </span></span>](http://doi.org/10.1007/s00200-008-0072-2)
- [<span data-ttu-id="2c149-119">*D. Coppersmith* arXiv: quant-pH/0201067v1</span><span class="sxs-lookup"><span data-stu-id="2c149-119"> *D. Coppersmith* arXiv:quant-ph/0201067v1 </span></span>](https://arxiv.org/abs/quant-ph/0201067)