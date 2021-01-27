---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Uživatelem definovaný typ LabeledSample
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846965"
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