---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698180"
---
# <a name="allequalityfacti-function"></a>AllEqualityFactI – funkce

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček [](https://nuget.org/packages/)


Vyhodnotí, že dvě pole celočíselných hodnot jsou shodná.

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a>Vstup

### <a name="actual--int"></a>skutečnost: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole, které je vytvořeno testovacím případem zájmu.


### <a name="expected--int"></a>očekáváno: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole, které je očekáváno z testovacího případu, který je předmětem zájmu.


### <a name="message--string"></a>zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)

Zpráva, která má být vytištěna v případě, že pole nejsou shodná.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

