---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Uživatelem definovaný typ LabeledSample
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196323"
---
# <a name="labeledsample-user-defined-type"></a>Uživatelem definovaný typ LabeledSample

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček: [Microsoft. MachineLearning.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Vzorek označený třídou, do které patří ukázka.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="features--double"></a>Funkce: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vektor funkcí pro danou ukázku.
### <a name="label--int"></a>Popisek: [int](xref:microsoft.quantum.lang-ref.int)

Celočíselný popisek třídy, ke které patří tato ukázka.