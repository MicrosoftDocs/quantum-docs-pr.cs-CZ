---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 1d7890e96513817c127ef768f49c0b915ea22fa1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858167"
---
# <a name="blockencodingbylcu-function"></a>BlockEncodingByLCU – funkce

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zakóduje operátor zájmu do `BlockEncoding` .

Tato konstrukce vytvoří `BlockEncoding` jednotkovou $U = P\cdot V\cdot P ^ \dagger $, který kóduje nějaký operátor $H = \ sum_ {j} | \ alpha_j | U_j $ z zájmu je lineární kombinací unitaries. $P $ je obvykle státní příprava, takže $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ a $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="statepreparation--t--unit--is-adj--ctl"></a>statePreparation: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Jednotková $P $, která připraví určitý cílový stav.


### <a name="selector--ts--unit--is-adj--ctl"></a>selektor: (t, ') => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Jednotková $V $, která kóduje komponentu unitaries $H $.



## <a name="output--ts--unit--is-adj--ctl"></a>Výstup: (t, 'S) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Jednotná $U $ pracuje společně na registrech `a` a `s` zablokuje $H $ a splňuje $U ^ \Dagger = U $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S


### <a name="s"></a>Jeho



## <a name="remarks"></a>Poznámky

Tato `BlockEncoding` implementace poskytuje vlastnosti `BlockEncodingReflection` .

## <a name="see-also"></a>Viz také

- [Microsoft. v. simulace. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. v. simulace. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)