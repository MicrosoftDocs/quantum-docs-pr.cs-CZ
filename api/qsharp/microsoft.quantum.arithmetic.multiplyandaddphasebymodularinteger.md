---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Operace MultiplyAndAddPhaseByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: be7df50f040697329c2fe8bbc319c8cebb8b2687
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706400"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a>Operace MultiplyAndAddPhaseByModularInteger

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Stejné jako MultiplyAndAddByModularInteger, ale předpokládá, že summand kóduje celá čísla v QFT základ.

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
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