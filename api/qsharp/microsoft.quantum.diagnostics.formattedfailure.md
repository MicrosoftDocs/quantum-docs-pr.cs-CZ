---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: da809c04059d4fd0f0ec92412a3094f5b582fd91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201695"
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