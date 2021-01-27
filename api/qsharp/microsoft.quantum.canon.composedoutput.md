---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: d39fcd6b2987b3a4f69df13fa83b69a199d6eddb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840892"
---
# <a name="composedoutput-function"></a>ComposedOutput – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

