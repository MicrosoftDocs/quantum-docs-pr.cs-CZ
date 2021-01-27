---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: a207ba1c4d08ec58095f5db34ee32c7341002920
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829176"
---
# <a name="equalityfactcp-function"></a>EqualityFactCP – funkce

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vyhodnotí, že komplexní číslo má očekávanou hodnotu.

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a>Vstup

### <a name="actual--complexpolar"></a>skutečnost: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Hodnota, která má být kontrolována.


### <a name="expected--complexpolar"></a>očekáváno: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Očekávaná hodnota.


### <a name="message--string"></a>zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)

Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

