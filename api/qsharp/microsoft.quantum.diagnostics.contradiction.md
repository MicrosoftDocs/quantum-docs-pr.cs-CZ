---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Odporující funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829367"
---
# <a name="contradiction-function"></a>Odporující funkce

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Deklaruje, že klasická podmínka je nepravdivá.

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Vstup

### <a name="actual--bool"></a>skutečnost: [bool](xref:microsoft.quantum.lang-ref.bool)

Podmínka, která má být deklarována.


### <a name="message--string"></a>zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)

Řetězec zprávy o selhání, který se má vytisknout v případě, že je klasická podmínka pravdivá



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Příklad

Následující kód Q # vypíše text "Hello, World":

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a>Viz také

- [Microsoft. provedl. Diagnostics. fakt](xref:Microsoft.Quantum.Diagnostics.Fact)