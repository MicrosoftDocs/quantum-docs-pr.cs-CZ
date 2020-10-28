---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697925"
---
# <a name="steanecode-function"></a><span data-ttu-id="2eb30-102">SteaneCode – funkce</span><span class="sxs-lookup"><span data-stu-id="2eb30-102">SteaneCode function</span></span>

<span data-ttu-id="2eb30-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="2eb30-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="2eb30-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2eb30-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2eb30-105">Vrátí hodnotu CSS reprezentující ⟦ 7, 1, 3 ⟧ Steane Code Encoder a dekodér s místním měřením Syndrome.</span><span class="sxs-lookup"><span data-stu-id="2eb30-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="2eb30-106">Výstup: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="2eb30-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="2eb30-107">Objekt typu CSS, který shromažďuje všechna relevantní data pro provádění kódování a opravy chyb pro kód Steane pro ⟦ 7, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="2eb30-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="2eb30-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2eb30-108">Remarks</span></span>

<span data-ttu-id="2eb30-109">Tento kód byl nalezen v následujícím dokumentu:</span><span class="sxs-lookup"><span data-stu-id="2eb30-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="2eb30-110">A.</span><span class="sxs-lookup"><span data-stu-id="2eb30-110">A.</span></span> <span data-ttu-id="2eb30-111">Steane, "vícenásobné rušení částic a náprava chyb, proc.</span><span class="sxs-lookup"><span data-stu-id="2eb30-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="2eb30-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="2eb30-112">Roy.</span></span> <span data-ttu-id="2eb30-113">SOC. Lond.</span><span class="sxs-lookup"><span data-stu-id="2eb30-113">Soc. Lond.</span></span> <span data-ttu-id="2eb30-114">A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="2eb30-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>