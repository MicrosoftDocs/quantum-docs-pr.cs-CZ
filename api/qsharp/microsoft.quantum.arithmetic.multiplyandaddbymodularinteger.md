---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: Operace MultiplyAndAddByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 169326879919b5b72d600c33d624776b720cc6bc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222588"
---
# <a name="multiplyandaddbymodularinteger-operation"></a>Operace MultiplyAndAddByModularInteger

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Provede modulární násobení a přidání celočíselnými konstantami v qubit registru.

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Implementuje mapu $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $ $ pro dané zbytky $N $, konstantní násobitel $a $ a summand $y $.

## <a name="input"></a>Vstup

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Do popisku každého základního stavu se přidá celé číslo $a $.


### <a name="modulus--int"></a>Modulus: [int](xref:microsoft.quantum.lang-ref.int)

Zbytky $N $, které přidávají a násobení, se provádí s ohledem na.


### <a name="multiplier--littleendian"></a>násobitel: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registr v bajtech představuje unsigned integer, jehož hodnota má být přidána do každého popisku stavu `summand` .


### <a name="summand--littleendian"></a>summand: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registr nečinnosti, který představuje unsigned integer, který se má použít jako cíl pro tuto operaci.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

- Pro diagram okruhu a vysvětlení, viz obrázek 6 na [stránce 7 arXiv: quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)
- Tato operace odpovídá funkci CMULT (a) MOD (N) v [arXiv: quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)

## <a name="see-also"></a>Viz také

- [Microsoft. prostředníky. aritmetické. MultiplyAndAddPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)