---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704352"
---
# <a name="composedoutput-function"></a>ComposedOutput – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vrátí výstup složení `inner` a `outer` pro daný vstup.

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a>Vstup

### <a name="outer--u---v"></a>vnější: U-> V




### <a name="inner--t---u"></a>vnitřní: t-> ' U




### <a name="target--t"></a>cíl: t





## <a name="output--v"></a>Výstup: ' V



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S


### <a name="u"></a>U


### <a name="v"></a>V

