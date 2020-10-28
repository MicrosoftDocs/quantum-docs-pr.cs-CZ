---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Uživatelem definovaný typ RequiresCapability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 63b1952d402f1bcb81a8f9d0afc3cdf7aa7e5ed8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709136"
---
# <a name="requirescapability-user-defined-type"></a>Uživatelem definovaný typ RequiresCapability

Obor názvů: [Microsoft. Protargeting](xref:Microsoft.Quantum.Targeting)

Balíček [](https://nuget.org/packages/)


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