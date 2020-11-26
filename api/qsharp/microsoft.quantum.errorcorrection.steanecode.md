---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: b981c82acfa82cd58d82666703d4bb95ac5df280
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200471"
---
# <a name="steanecode-function"></a><span data-ttu-id="341ef-102">SteaneCode – funkce</span><span class="sxs-lookup"><span data-stu-id="341ef-102">SteaneCode function</span></span>

<span data-ttu-id="341ef-103">Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="341ef-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="341ef-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="341ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="341ef-105">Vrátí hodnotu CSS reprezentující ⟦ 7, 1, 3 ⟧ Steane Code Encoder a dekodér s místním měřením Syndrome.</span><span class="sxs-lookup"><span data-stu-id="341ef-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="341ef-106">Výstup: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="341ef-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="341ef-107">Objekt typu CSS, který shromažďuje všechna relevantní data pro provádění kódování a opravy chyb pro kód Steane pro ⟦ 7, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="341ef-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="341ef-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="341ef-108">Remarks</span></span>

<span data-ttu-id="341ef-109">Tento kód byl nalezen v následujícím dokumentu:</span><span class="sxs-lookup"><span data-stu-id="341ef-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="341ef-110">A.</span><span class="sxs-lookup"><span data-stu-id="341ef-110">A.</span></span> <span data-ttu-id="341ef-111">Steane, "vícenásobné rušení částic a náprava chyb, proc.</span><span class="sxs-lookup"><span data-stu-id="341ef-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="341ef-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="341ef-112">Roy.</span></span> <span data-ttu-id="341ef-113">SOC. Lond.</span><span class="sxs-lookup"><span data-stu-id="341ef-113">Soc. Lond.</span></span> <span data-ttu-id="341ef-114">A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="341ef-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>