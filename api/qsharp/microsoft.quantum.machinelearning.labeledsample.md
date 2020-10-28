---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Uživatelem definovaný typ LabeledSample
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697684"
---
# <a name="labeledsample-user-defined-type"></a>Uživatelem definovaný typ LabeledSample

Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)

Balíček [](https://nuget.org/packages/)


Vzorek označený třídou, do které patří ukázka.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Pojmenované položky

### <a name="features--double"></a>Funkce: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vektor funkcí pro danou ukázku.
### <a name="label--int"></a>Popisek: [int](xref:microsoft.quantum.lang-ref.int)

Celočíselný popisek třídy, ke které patří tato ukázka.