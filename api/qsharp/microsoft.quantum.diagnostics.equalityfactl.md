---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: b7d37b5115c51596c1b3ed93c53a29e9f36b811d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829147"
---
# <a name="equalityfactl-function"></a>EqualityFactL – funkce

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vyhodnotí, že klasická hodnota typu BigInt má očekávanou hodnotu.

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a>Vstup

### <a name="actual--bigint"></a>skutečnost: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Číslo, které má být zkontrolováno.


### <a name="expected--bigint"></a>očekáváno: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Očekávaná hodnota.


### <a name="message--string"></a>zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)

Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

