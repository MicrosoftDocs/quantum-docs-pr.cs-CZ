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
# <a name="steanecode-function"></a>SteaneCode – funkce

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček [](https://nuget.org/packages/)


Vrátí hodnotu CSS reprezentující ⟦ 7, 1, 3 ⟧ Steane Code Encoder a dekodér s místním měřením Syndrome.

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>Výstup: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Objekt typu CSS, který shromažďuje všechna relevantní data pro provádění kódování a opravy chyb pro kód Steane pro ⟦ 7, 1, 3 ⟧.

## <a name="remarks"></a>Poznámky

Tento kód byl nalezen v následujícím dokumentu:

- A. Steane, "vícenásobné rušení částic a náprava chyb, proc. Roy. SOC. Lond. A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.