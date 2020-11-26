---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Uživatelem definovaný typ RequiresCapability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 0d9e4eb294b3ce91058c204d5dba37ea29b4ac28
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231003"
---
# <a name="requirescapability-user-defined-type"></a>Uživatelem definovaný typ RequiresCapability

Obor názvů: [Microsoft. Protargeting](xref:Microsoft.Quantum.Targeting)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Atribut rozpoznaný kompilátorem, který slouží k označení možného možného spuštění s běhovými funkcemi, které vyžaduje.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="level--string"></a>Level: [String](xref:microsoft.quantum.lang-ref.string)

Název úrovně běhové funkce, kterou vyžaduje možnost volat.
### <a name="reason--string"></a>Důvod: [řetězec](xref:microsoft.quantum.lang-ref.string)

Popis důvodu, proč vyžaduje tuto možnost spuštění.

## <a name="remarks"></a>Poznámky

Tento atribut je automaticky přidán pro volání kompilátorem, pokud instance tohoto atributu již na volání nelze navolat. Neměl by být použit kromě výjimečných případů, kdy kompilátor neodvodí požadovanou funkci správně.

Níže je uveden seznam názvů úrovní schopností, v pořadí rostoucích možností nebo snížení omezení:

## `"BasicQuantumFunctionality"`

Výsledky měření nejde porovnávat s rovností.

## `"BasicMeasurementFeedback"`

Výsledky měření lze porovnat pouze s rovností v podmíněných výrazech if-Statement v operacích. Blok if příkazu, který závisí na výsledku, nemůže obsahovat příkazy set pro proměnlivé proměnné deklarované mimo blok nebo příkazy Return.

## `"FullComputation"`

Žádná běhová omezení. Můžete spustit libovolný program Q #.