---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 84dc132528f8fd1c45fb2f7345111a05626ee686
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839628"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx – funkce

Obor názvů: [Microsoft.. chemie](xref:Microsoft.Quantum.Chemistry)

Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Převede index na Hamiltonian termín ve `HTerm[]` formátu dat na GeneratorIndex.

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Vstup

### <a name="data--hterm"></a>data: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Vstupní data ve `HTerm[]` formátu.


### <a name="termtype--int"></a>termType: [int](xref:microsoft.quantum.lang-ref.int)[]

Další informace přidané do GeneratorIndex


### <a name="idx--int"></a>IDX: [int](xref:microsoft.quantum.lang-ref.int)

Index na termín Hamiltonian



## <a name="output--generatorindex"></a>Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

GeneratorIndex reprezentující Hamiltonian termín, který představuje `data[idx]` , spolu s dalšími informacemi, které přidal `termType` .