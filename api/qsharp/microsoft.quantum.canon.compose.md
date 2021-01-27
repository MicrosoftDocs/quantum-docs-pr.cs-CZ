---
uid: Microsoft.Quantum.Canon.Compose
title: Funkce pro vytváření
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840906"
---
# <a name="compose-function"></a>Funkce pro vytváření

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí kompozici dvou funkcí.

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>Popis

Zadané dvě funkce $f $ a $g $, vrátí novou funkci reprezentující $f \circ g $.

## <a name="input"></a>Vstup

### <a name="outer--u---v"></a>vnější: U-> V

Druhá funkce, která má být použita.


### <a name="inner--t---u"></a>vnitřní: t-> ' U

První funkce, která se má použít



## <a name="output--t---v"></a>Výstup: t-> ' V

Nová funkce $h $, což pro všechny vstupy $x $, $f (g (x)) = h (x) $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ první funkce, která má být použita.
### <a name="u"></a>U

Typ výstupu první funkce, která má být použita, a vstupní typ druhé funkce, která má být použita.
### <a name="v"></a>V

Typ výstupu druhé funkce, která má být použita.