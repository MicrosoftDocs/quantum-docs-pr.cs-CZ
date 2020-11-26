---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: f8d102cd54222f61058c655e72c63e86d2f5af03
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201202"
---
# <a name="bitfliprecoveryfn-function"></a><span data-ttu-id="0feba-102">BitFlipRecoveryFn – funkce</span><span class="sxs-lookup"><span data-stu-id="0feba-102">BitFlipRecoveryFn function</span></span>

<span data-ttu-id="0feba-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="0feba-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="0feba-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0feba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0feba-105">Funkce pro obnovení Pauli operací pro dané měření Syndrome podle vyhledávání tabulek pro ⟦ 3, 1, 1 ⟧ bit překlápění kódu.</span><span class="sxs-lookup"><span data-stu-id="0feba-105">Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.</span></span>

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="0feba-106">Výstup: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="0feba-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="0feba-107">Funkce typu `RecoveryFn` , která přijímá Syndrome měření `Result[]` a vrací `Pauli[]` operace, které opraví zjištěnou chybu.</span><span class="sxs-lookup"><span data-stu-id="0feba-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="0feba-108">Viz také</span><span class="sxs-lookup"><span data-stu-id="0feba-108">See Also</span></span>

- [<span data-ttu-id="0feba-109">Microsoft. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="0feba-109">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)