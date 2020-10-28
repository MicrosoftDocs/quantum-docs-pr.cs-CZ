---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: Operace KnillDistill
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 1135db83cf750918347df10c6f1301b636aaee0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697953"
---
# <a name="knilldistill-operation"></a><span data-ttu-id="97fd1-102">Operace KnillDistill</span><span class="sxs-lookup"><span data-stu-id="97fd1-102">KnillDistill operation</span></span>

<span data-ttu-id="97fd1-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="97fd1-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="97fd1-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="97fd1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="97fd1-105">Implementuje algoritmus Knill Magic State.</span><span class="sxs-lookup"><span data-stu-id="97fd1-105">Implements the Knill magic state distillation algorithm.</span></span>

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a><span data-ttu-id="97fd1-106">Popis</span><span class="sxs-lookup"><span data-stu-id="97fd1-106">Description</span></span>

<span data-ttu-id="97fd1-107">Vzhledem k 15 přibližným kopiím stavu Magic $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} \end{align}, $ $ vytvoří jednu kopii s vyšší kvalitou.</span><span class="sxs-lookup"><span data-stu-id="97fd1-107">Given 15 approximate copies of a magic state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1} \end{align}, $$ yields one higher-quality copy.</span></span>

## <a name="input"></a><span data-ttu-id="97fd1-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="97fd1-108">Input</span></span>

### <a name="roughmagic--qubit"></a><span data-ttu-id="97fd1-109">roughMagic: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="97fd1-109">roughMagic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="97fd1-110">Registr 15 qubits obsahujících přibližné kopie stavu Magic.</span><span class="sxs-lookup"><span data-stu-id="97fd1-110">A register of fifteen qubits containing approximate copies of a magic state.</span></span> <span data-ttu-id="97fd1-111">Po použití tohoto postupu je potřeba, aby `roughMagic[0]` obsahovalo jednu kopii s vyšší kvalitou a zbytek registru se resetoval na stav $ \ket{00\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="97fd1-111">Following application of this distillation procedure, `roughMagic[0]` will contain one higher-quality copy, and the rest of the register will be reset to the $\ket{00\cdots 0}$ state.</span></span>



## <a name="output--bool"></a><span data-ttu-id="97fd1-112">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="97fd1-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="97fd1-113">Pokud byl `true` postup úspěšný a je třeba přijmout kopii vyšší kvality.</span><span class="sxs-lookup"><span data-stu-id="97fd1-113">If `true`, then the procedure succeeded and the higher-quality copy should be accepted.</span></span> <span data-ttu-id="97fd1-114">Pokud `false` se procedura nezdařila a stav registru by měl být považován za nedefinovaný.</span><span class="sxs-lookup"><span data-stu-id="97fd1-114">If `false`, the procedure failed, and the state of the register should be considered undefined.</span></span>

## <a name="remarks"></a><span data-ttu-id="97fd1-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="97fd1-115">Remarks</span></span>

<span data-ttu-id="97fd1-116">Sledujeme algoritmus Knill.</span><span class="sxs-lookup"><span data-stu-id="97fd1-116">We follow the algorithm of Knill.</span></span>
<span data-ttu-id="97fd1-117">Nicméně Současná implementace je daleko od optimálního, protože používá příliš mnoho qubits.</span><span class="sxs-lookup"><span data-stu-id="97fd1-117">However, the present implementation is far from being optimal, as it uses too many qubits.</span></span>
<span data-ttu-id="97fd1-118">V této rutině jsou vloženy stavy Magic. v takovém případě jsou k dispozici lepší protokoly.</span><span class="sxs-lookup"><span data-stu-id="97fd1-118">The magic states are injected in this routine, in which case there are better protocols.</span></span>

## <a name="references"></a><span data-ttu-id="97fd1-119">Odkazy</span><span class="sxs-lookup"><span data-stu-id="97fd1-119">References</span></span>

- [<span data-ttu-id="97fd1-120">Knill</span><span class="sxs-lookup"><span data-stu-id="97fd1-120">Knill</span></span>](https://arxiv.org/abs/quant-ph/0402171)