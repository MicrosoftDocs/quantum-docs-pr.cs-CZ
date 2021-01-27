---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fakt – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853306"
---
# <a name="fact-function"></a>Fakt – funkce

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Deklaruje, že klasická podmínka je pravdivá.

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Vstup

### <a name="actual--bool"></a>skutečnost: [bool](xref:microsoft.quantum.lang-ref.bool)

Podmínka, která má být deklarována.


### <a name="message--string"></a>zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)

Řetězec zprávy o selhání, který se má vytisknout v případě, že je klasická podmínka nepravdivá



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Příklad

Následující fragment kódu Q # se nezdaří:

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a>Viz také

- [Microsoft. prověří. Diagnostics. rozpor](xref:Microsoft.Quantum.Diagnostics.Contradiction)