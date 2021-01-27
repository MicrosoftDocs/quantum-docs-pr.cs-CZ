---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: DefaultTrainingOptions – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855992"
---
# <a name="defaulttrainingoptions-function"></a>DefaultTrainingOptions – funkce

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vrátí výchozí sadu možností pro účely školení klasifikátorů.

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a>Výstup: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Přiměřená sada výchozích možností školení pro použití při výuce klasifikátorů.

## <a name="example"></a>Příklad

Chcete-li použít výchozí možnosti, ale s dalšími měřeními, použijte `w/` operátor:

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```