---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 414b703151b9152aa69709d9c28e68e5ae63506f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228861"
---
# <a name="withzeroinsertedat-function"></a>WithZeroInsertedAt – funkce

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vložení 0 bitové čárky do celého čísla

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a>Popis

Tato operace přebírá celé číslo, vloží hodnotu 0 v bitu `position` a vrátí aktualizovanou hodnotu jako celé číslo.  Například vložení 0 na pozici 2 v numberu 10 (100 USD _ {10} = 1010_ {2} $) vrátí číslo 18 ($18 _ {10} = 10010_ {2} $).

## <a name="input"></a>Vstup

### <a name="position--int"></a>pozice: [int](xref:microsoft.quantum.lang-ref.int)

Pozice, na kterou je vložen 0


### <a name="value--int"></a>hodnota: [int](xref:microsoft.quantum.lang-ref.int)

Hodnota, která je změněna



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Upravená hodnota