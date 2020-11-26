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
# <a name="steanecode-function"></a>SteaneCode – funkce

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí hodnotu CSS reprezentující ⟦ 7, 1, 3 ⟧ Steane Code Encoder a dekodér s místním měřením Syndrome.

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>Výstup: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Objekt typu CSS, který shromažďuje všechna relevantní data pro provádění kódování a opravy chyb pro kód Steane pro ⟦ 7, 1, 3 ⟧.

## <a name="remarks"></a>Poznámky

Tento kód byl nalezen v následujícím dokumentu:

- A. Steane, "vícenásobné rušení částic a náprava chyb, proc. Roy. SOC. Lond. A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.