---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698089"
---
# <a name="equalityfactl-function"></a>EqualityFactL – funkce

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček [](https://nuget.org/packages/)


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

