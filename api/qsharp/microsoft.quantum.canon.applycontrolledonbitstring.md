---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Operace ApplyControlledOnBitString
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 6947d2dbdec4cfbb592143024a7c8ccd53a32029
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219069"
---
# <a name="applycontrolledonbitstring-operation"></a>Operace ApplyControlledOnBitString

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje v cílovém registru jednotnou operaci řízenou v určitém stavu určeném příslušnou bitovou maskou.

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="bits--bool"></a>bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Bitový řetězec, na kterém se má řídit daná Jednotková operace.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Jednotná operace, která se má použít v cílovém registru.


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Každé z nich registruje registraci řízení aplikací `oracle` .


### <a name="targetregister--t"></a>targetRegister: 'T

Cílový registr, který má být předán `oracle` jako vstup.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="remarks"></a>Poznámky

Vzor zadaný pomocí `bits` může být kratší než `controlRegister` , v takovém případě je další qubits ovládacího prvku ignorováno (to znamená, že není kontrolováno na $ \ket {0} $ ani $ \ket {1} $).
Pokud `bits` je delší než `controlRegister` , je vyvolána chyba.

Například `bits = [0,1,0,0,1]` to znamená, že `oracle` se použije pouze v případě, že `controlRegister` je ve stavu $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.