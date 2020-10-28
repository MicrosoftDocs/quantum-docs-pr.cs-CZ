---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: ca5a6e116eff187060f7a160e42836b170f0362d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704328"
---
# <a name="controlledonbitstring-function"></a>ControlledOnBitString – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vrátí jednotnou operaci, která použije Oracle v cílovém registru, pokud stav registru ovládacího prvku odpovídá zadané bitové masce.

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>Popis

Výstupem této funkce je operace, kterou může představovat jednotná transformace $U $ taková, že \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{BITS} \\ \\ \ket{\psi} & \textrm{Otherwise} \end{Cases}, \end{align}, kde $V $ je jednotná transformace, která představuje akci `oracle` operace.

## <a name="input"></a>Vstup

### <a name="bits--bool"></a>bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Bitový řetězec, na kterém se má řídit daná Jednotková operace.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Jednotná operace, která se má použít v cílovém registru.



## <a name="output--qubitt--unit-adj--ctl"></a>Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Jednotná operace, která platí `oracle` v cílovém registru, pokud stav registru ovládacího prvku odpovídá bitové masce `bits` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="remarks"></a>Poznámky

Vzor zadaný pomocí `bits` může být kratší než `controlRegister` , v takovém případě je další qubits ovládacího prvku ignorováno (to znamená, že není kontrolováno na $ \ket {0} $ ani $ \ket {1} $).
Pokud `bits` je delší než `controlRegister` , je vyvolána chyba.

V případě logického pole `bits` a jednotkové operace `oracle` je výstup této funkce operace, která provede následující kroky:

* použijte `X` operaci na každý qubit registru ovládacího prvku, který odpovídá `false` elementu `bits` .
* platí `Controlled oracle` pro Registry ovládacího prvku a cíle;
* použijte `X` operaci na každý qubit registru ovládacího prvku, který odpovídá `false` elementu `bits` znovu a vrátí registraci ovládacího prvku do původního stavu.

Výstupem `Controlled` funktor je zvláštní případ, `ControlledOnBitString` kde `bits` je rovno `[true, ..., true]` .