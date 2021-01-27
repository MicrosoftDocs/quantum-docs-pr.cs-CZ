---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828281"
---
# <a name="formattedfailure-function"></a>FormattedFailure – funkce

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vnitřní funkce používaná k selhání s smysluplnými chybovými zprávami.

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a>Vstup

### <a name="actual--t"></a>skutečnost: t




### <a name="expected--t"></a>očekáváno: t




### <a name="message--string"></a>zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)





## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="remarks"></a>Poznámky

Tato funkce má být emulovaná modulem runtime simulace, aby bylo možné předávat naformátované odpory.