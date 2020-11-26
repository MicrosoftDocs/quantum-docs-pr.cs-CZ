---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Operace MultiplyAndAddPhaseByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: 1ca20b525d2a76e554d5a2e8d4f40060b5ef51cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223863"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a>Operace MultiplyAndAddPhaseByModularInteger

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stejné jako MultiplyAndAddByModularInteger, ale předpokládá, že summand kóduje celá čísla v QFT základ.

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Do popisku každého základního stavu se přidá celé číslo $a $.


### <a name="modulus--int"></a>Modulus: [int](xref:microsoft.quantum.lang-ref.int)

Zbytky $N $, které přidávají a násobení, se provádí s ohledem na.


### <a name="multiplier--littleendian"></a>násobitel: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registr v bajtech představuje unsigned integer, jehož hodnota má být přidána do každého popisku stavu `summand` .


### <a name="phasesummand--phaselittleendian"></a>phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Registr nečinnosti, který představuje unsigned integer, který se má použít jako cíl pro tuto operaci.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Předpokládá, že `phaseSummand` má nejvyšší bit nastavený na hodnotu 0.
Také předpokládá, že hodnota `phaseSummand` je menší než $N $.

## <a name="see-also"></a>Viz také

- [Microsoft. prostředníky. aritmetické. MultiplyAndAddByModularInteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)