---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: cb1d4c471c528d2d3c08c92619fafd532a88c8f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829206"
---
# <a name="equalityfactb-function"></a>EqualityFactB – funkce

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vyhodnotí, že klasická proměnná bool má očekávanou hodnotu.

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a>Vstup

### <a name="actual--bool"></a>skutečnost: [bool](xref:microsoft.quantum.lang-ref.bool)

Proměnná, která se má zkontrolovat


### <a name="expected--bool"></a>očekáváno: [bool](xref:microsoft.quantum.lang-ref.bool)

Očekávaná hodnota.


### <a name="message--string"></a>zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)

Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

