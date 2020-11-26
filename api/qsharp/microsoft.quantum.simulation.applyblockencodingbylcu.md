---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Operace ApplyBlockEncodingByLCU
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 8ce6eb16b1dc5a83dd3a9559592c20d6b7b999b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225478"
---
# <a name="applyblockencodingbylcu-operation"></a>Operace ApplyBlockEncodingByLCU

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementace `BlockEncodingByLCU` .

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="statepreparation--t--unit--is-adj--ctl"></a>statePreparation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL




### <a name="selector--ts--unit--is-adj--ctl"></a>selektor: (t, ') => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL




### <a name="auxiliary--t"></a>Pomocná: t




### <a name="system--s"></a>System: 'S





## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S


### <a name="s"></a>Jeho

