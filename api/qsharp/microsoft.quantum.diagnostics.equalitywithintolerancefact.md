---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: ab7e43d951bf741926b15f27f94d176e88609d4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828754"
---
# <a name="equalitywithintolerancefact-function"></a>EqualityWithinToleranceFact – funkce

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Představuje deklaraci identity, že klasická hodnota s plovoucí desetinnou čárkou má očekávanou hodnotu až do dané absolutní tolerance.

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a>Vstup

### <a name="actual--double"></a>skutečnost: [Double](xref:microsoft.quantum.lang-ref.double)

Číslo, které má být zkontrolováno.


### <a name="expected--double"></a>očekáváno: [Double](xref:microsoft.quantum.lang-ref.double)

Očekávaná hodnota.


### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

Absolutní tolerance rozdílu mezi skutečnými a očekávanými hodnotami.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

