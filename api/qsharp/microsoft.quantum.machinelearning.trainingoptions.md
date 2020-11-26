---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: Uživatelem definovaný typ TrainingOptions
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 280a3857aa7bc42f636a33f893d4f450e79b6a6a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196119"
---
# <a name="trainingoptions-user-defined-type"></a>Uživatelem definovaný typ TrainingOptions

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Kolekce možností, které se mají použít při výuce klasifikátorů

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a>Pojmenované položky

### <a name="learningrate--double"></a>LearningRate: [Double](xref:microsoft.quantum.lang-ref.double)

Míra učení, podle které se při aktualizaci parametrů modelu během školicích kroků má změnit velikost přechodů.
### <a name="tolerance--double"></a>Tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerance aproximace, která se má použít při přípravě ukázek jako stavové stavy.
### <a name="minibatchsize--int"></a>MinibatchSize: [int](xref:microsoft.quantum.lang-ref.int)

Počet vzorků, které se mají použít při každém školení minibatch.
### <a name="nmeasurements--int"></a>NMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Počet, kolikrát se má každý výsledek klasifikace změřit, aby se mohla odhadnout pravděpodobnost klasifikace
### <a name="maxepochs--int"></a>MaxEpochs: [int](xref:microsoft.quantum.lang-ref.int)

Maximální počet epochs, pro které se mají vyškolit jednotlivé modely
### <a name="maxstalls--int"></a>MaxStalls: [int](xref:microsoft.quantum.lang-ref.int)

Maximální počet pokusů, které epocha školení smí zablokovat (přibližně nula přechodu) před selháním.
### <a name="stochasticrescalefactor--double"></a>StochasticRescaleFactor: [Double](xref:microsoft.quantum.lang-ref.double)

Množství, které má znovu škálovat zastavené modely, před opakováním aktualizace.
### <a name="scoringperiod--int"></a>ScoringPeriod: [int](xref:microsoft.quantum.lang-ref.int)

Počet kroků přechodu mezi body bodování.
Pro nejlepší přesnost nastavte na hodnotu 1.
### <a name="verbosemessage--string---unit"></a>VerboseMessage: [String](xref:microsoft.quantum.lang-ref.string) -> [jednotka](xref:microsoft.quantum.lang-ref.unit) řetězce

Funkce, která může být použita k poskytnutí podrobné zpětné vazby.

## <a name="remarks"></a>Poznámky

Tento parametr UDT by neměl být vytvořen přímo, ale je třeba jej zadat voláním @"microsoft.quantum.machinelearning.defaulttrainingoptions" a poté pomocí `w/` operátoru přepsat jiné výchozí hodnoty.

Například pro použití měření 100 000 a maximálně 8 školicích epochs:

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a>Reference

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)