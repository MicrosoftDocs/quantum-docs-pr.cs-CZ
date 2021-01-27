---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 540dcf1eafa7449f386676a9a3c9562a4d4bf29c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853146"
---
# <a name="fivequbitcode-function"></a>FiveQubitCode – funkce

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrací hodnotu QECC představující ⟦ 5, 1, 3 ⟧ Code Encoder a dekodér s místním měřením Syndrome.

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>Výstup: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

Vrací implementaci kódu opravy chyb pro každé z nich zadáním `QECC` typu.

## <a name="remarks"></a>Poznámky

Tento kód byl nalezen nezávisle v následujících dvou dokladech:

- C. Y. Bennett, D. DiVincenzo, J. A. Smolin a W. K Wootters, "smíšených stavových entanglement a oprav chyb při chybě," fyz. rev. A, 54 (1996) PP. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 a
- Í. Laflamme, C. Miquel, J. P. Paz a W. H. Zurek, "dokonalý kód pro opravování chyb," fyz. rev. Lett. 77 (1996) PP. 198-201; https://arxiv.org/abs/quant-ph/9602019