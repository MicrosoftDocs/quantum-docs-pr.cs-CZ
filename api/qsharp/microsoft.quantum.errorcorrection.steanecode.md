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