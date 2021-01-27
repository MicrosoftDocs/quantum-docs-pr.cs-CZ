---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853061"
---
# <a name="steanecode-function"></a><span data-ttu-id="dc310-102">SteaneCode – funkce</span><span class="sxs-lookup"><span data-stu-id="dc310-102">SteaneCode function</span></span>

<span data-ttu-id="dc310-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="dc310-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="dc310-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc310-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc310-105">Vrátí hodnotu CSS reprezentující ⟦ 7, 1, 3 ⟧ Steane Code Encoder a dekodér s místním měřením Syndrome.</span><span class="sxs-lookup"><span data-stu-id="dc310-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="dc310-106">Výstup: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="dc310-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="dc310-107">Objekt typu CSS, který shromažďuje všechna relevantní data pro provádění kódování a opravy chyb pro kód Steane pro ⟦ 7, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="dc310-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="dc310-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="dc310-108">Remarks</span></span>

<span data-ttu-id="dc310-109">Tento kód byl nalezen v následujícím dokumentu:</span><span class="sxs-lookup"><span data-stu-id="dc310-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="dc310-110">A.</span><span class="sxs-lookup"><span data-stu-id="dc310-110">A.</span></span> <span data-ttu-id="dc310-111">Steane, "vícenásobné rušení částic a náprava chyb, proc.</span><span class="sxs-lookup"><span data-stu-id="dc310-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="dc310-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="dc310-112">Roy.</span></span> <span data-ttu-id="dc310-113">SOC. Lond.</span><span class="sxs-lookup"><span data-stu-id="dc310-113">Soc. Lond.</span></span> <span data-ttu-id="dc310-114">A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="dc310-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>