---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697972"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="602b0-102">FiveQubitCode – funkce</span><span class="sxs-lookup"><span data-stu-id="602b0-102">FiveQubitCode function</span></span>

<span data-ttu-id="602b0-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="602b0-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="602b0-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="602b0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="602b0-105">Vrací hodnotu QECC představující ⟦ 5, 1, 3 ⟧ Code Encoder a dekodér s místním měřením Syndrome.</span><span class="sxs-lookup"><span data-stu-id="602b0-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="602b0-106">Výstup: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="602b0-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="602b0-107">Vrací implementaci kódu opravy chyb pro každé z nich zadáním `QECC` typu.</span><span class="sxs-lookup"><span data-stu-id="602b0-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="602b0-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="602b0-108">Remarks</span></span>

<span data-ttu-id="602b0-109">Tento kód byl nalezen nezávisle v následujících dvou dokladech:</span><span class="sxs-lookup"><span data-stu-id="602b0-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="602b0-110">C.</span><span class="sxs-lookup"><span data-stu-id="602b0-110">C.</span></span> <span data-ttu-id="602b0-111">Y.</span><span class="sxs-lookup"><span data-stu-id="602b0-111">H.</span></span> <span data-ttu-id="602b0-112">Bennett, D. DiVincenzo, J. A.</span><span class="sxs-lookup"><span data-stu-id="602b0-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="602b0-113">Smolin a W. K</span><span class="sxs-lookup"><span data-stu-id="602b0-113">Smolin and W. K.</span></span> <span data-ttu-id="602b0-114">Wootters, "smíšených stavových entanglement a oprav chyb při chybě," fyz. rev. A, 54 (1996) PP. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 a</span><span class="sxs-lookup"><span data-stu-id="602b0-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="602b0-115">Í.</span><span class="sxs-lookup"><span data-stu-id="602b0-115">R.</span></span> <span data-ttu-id="602b0-116">Laflamme, C. Miquel, J. P.</span><span class="sxs-lookup"><span data-stu-id="602b0-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="602b0-117">Paz a W. H.</span><span class="sxs-lookup"><span data-stu-id="602b0-117">Paz and W. H.</span></span> <span data-ttu-id="602b0-118">Zurek, "dokonalý kód pro opravování chyb," fyz. rev. Lett.</span><span class="sxs-lookup"><span data-stu-id="602b0-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="602b0-119">77 (1996) PP. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="602b0-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>