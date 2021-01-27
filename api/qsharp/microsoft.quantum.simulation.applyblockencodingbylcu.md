---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Operace ApplyBlockEncodingByLCU
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852815"
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

