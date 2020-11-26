---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 254ace01750f94e6c871de9b62f1342000bc84ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229541"
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