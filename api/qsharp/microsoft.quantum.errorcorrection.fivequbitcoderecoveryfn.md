---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 5b8afe222d197eb7d342ac45f027f2de9130b61a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697968"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="03f90-102">FiveQubitCodeRecoveryFn – funkce</span><span class="sxs-lookup"><span data-stu-id="03f90-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="03f90-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="03f90-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="03f90-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="03f90-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="03f90-105">Vrátí funkci, která mapuje Syndrome o chybách na odpovídající chybu – správné správnosti Paulich operátorů podle vyhledávání v tabulce pro kód ⟦ 5, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="03f90-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="03f90-106">Výstup: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="03f90-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="03f90-107">Funkce typu `RecoveryFn` , která přijímá Syndrome měření `Result[]` a vrací `Pauli[]` operátory, které opraví zjištěnou chybu.</span><span class="sxs-lookup"><span data-stu-id="03f90-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="03f90-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="03f90-108">Remarks</span></span>

<span data-ttu-id="03f90-109">Díky iteraci všech chyb s váhou $1 $ získáme celkem $3 \ krát 5 = 15 $ možné netriviální Syndromes.</span><span class="sxs-lookup"><span data-stu-id="03f90-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="03f90-110">Společně s identitou je sestavena tabulka Error a odpovídající Syndrome.</span><span class="sxs-lookup"><span data-stu-id="03f90-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="03f90-111">Pro kód 5 qubit, na který je tato tabulka dána: $X \_ 1: (0, 0, 0, 1); X \_ 2: (1, 0, 0, 0); × \_ 3: (1, 1, 0, 0); × \_ 4: (0, 1, 1, 0); X \_ 5: (0, 0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0, 0, 1, 0); Z \_ 4: (1, 0, 0, 1); Z \_ 5: (0, 1, 0, 0) $ s $Y _i $ získá přidáním $X _i $ a $Z _i $ Syndromes.</span><span class="sxs-lookup"><span data-stu-id="03f90-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="03f90-112">Všimněte si, že pořadí při obnovení tabulky je předané převedením bitvectors na celá čísla (s použitím Little Endian).</span><span class="sxs-lookup"><span data-stu-id="03f90-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="03f90-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="03f90-113">See Also</span></span>

- [<span data-ttu-id="03f90-114">Microsoft. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="03f90-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)