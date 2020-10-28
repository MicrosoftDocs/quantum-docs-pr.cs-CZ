---
uid: Microsoft.Quantum.Canon.Compose
title: Funkce pro vytváření
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704353"
---
# <a name="compose-function"></a>Funkce pro vytváření

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


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